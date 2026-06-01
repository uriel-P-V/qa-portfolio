# BUG-010 — Upload is 37x slower than download — performance deviation

## Environment
- OS: Windows 10
- Python: 3.13
- Docker Desktop
- MinIO Community Edition (quay.io/minio/minio)
- pytest 9.0.3
- pytest-benchmark 5.2.3
- Project: minio-storage-tests

## Severity
Medium

## Priority
P2

## Steps to Reproduce
1. Start MinIO container:
   ```bash
   docker start minio
   ```
2. Run performance tests:
   ```bash
   pytest tests/test_performance.py -v
   ```
3. Observe benchmark results for upload vs download mean latency

## Expected Behavior
Both upload and download operations should complete within the 200ms threshold defined in the test suite.

```
test_object_upload_performance   Mean < 200ms
test_object_download_performance Mean < 200ms
```

## Actual Behavior
Upload latency significantly exceeds the 200ms threshold and is 37x slower than download:

| Operation | Min | Mean | Max | OPS |
|-----------|-----|------|-----|-----|
| Download | 1.03ms | 1.40ms | 4.16ms | 714/s |
| Bucket creation | 5.40ms | 6.18ms | 8.64ms | 162/s |
| **Upload** | **47.24ms** | **47.95ms** | **49.01ms** | **21/s** |

**Upload/Download ratio: 34x slower**

The upload test passes because 47.95ms is under the 200ms threshold,
but the performance gap between upload and download is significant.

## Impact
- Upload throughput is limited to ~21 operations per second
- In high-volume storage scenarios, upload bottleneck reduces system throughput
- 34x latency difference makes upload the critical path in any storage pipeline
- Affects backup systems, log ingestion and any write-heavy workloads

## Notes
Upload latency being higher than download is **partially expected behavior**
in object storage systems — upload requires:
- Writing data to disk
- Computing and validating checksum
- Updating object metadata

However, the 34x ratio exceeds typical upload/download ratios in
well-configured MinIO instances (usually 2-5x).

**Recommended investigation:**
- Review MinIO write buffer configuration
- Check disk I/O performance on the Docker volume
- Consider enabling direct I/O mode for better write performance

This was identified via `pytest-benchmark` in `minio-storage-tests`.
The upload test passes its 200ms threshold but the performance gap
warrants investigation before production deployment.

## Attachments
- pytest-benchmark output
- Performance test source: `tests/test_performance.py`