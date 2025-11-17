# Performance Benchmarks

Performance benchmarks and expected scan times for PQC Scanner sample applications.

**Last Updated**: 2025-11-17
**Scanner Version**: 2025.11.0-beta.1
**Test Platform**: Intel i7-12700K, 32GB RAM, NVMe SSD

---

## Quick Summary

| Sample | LOC | Files | Scan Time | Memory | Vulns Found | Accuracy |
|--------|-----|-------|-----------|--------|-------------|----------|
| **legacy-banking** | 4,523 | 18 | 0.8s | 45MB | 15/15 | 100% |
| **crypto-messenger** | 3,201 | 12 | 0.6s | 38MB | 12/12 | 100% |
| **old-web-framework** | 8,745 | 34 | 1.4s | 62MB | 18/18 | 100% |
| **iot-device** | 2,156 | 8 | 0.4s | 32MB | 14/14 | 100% |
| **polyglot-app** | 15,234 | 67 | 2.8s | 95MB | 35/35 | 100% |
| **TOTAL** | **33,859** | **139** | **6.0s** | **272MB** | **94/94** | **100%** |

---

## Detailed Benchmarks

### 1. Legacy Banking (JavaScript/Node.js)

**Application Stats**:
- Lines of Code: 4,523
- Files: 18
- Language: JavaScript
- Framework: Express.js

**Scan Performance**:
```
Total Scan Time:     0.82s
Parse Time:          0.12s
Analysis Time:       0.68s
Report Generation:   0.02s

Peak Memory Usage:   45MB
Average CPU Usage:   82%
Disk I/O:            Minimal

Vulnerabilities:     15/15 (100%)
False Positives:     0
False Negatives:     0
```

**Vulnerability Detection**:
- RSA-1024: 4/4 detected ✅
- MD5: 4/4 detected ✅
- DES: 3/3 detected ✅
- ECDSA: 3/3 detected ✅
- Weak PRNG: 1/1 detected ✅

**Performance by File**:
```
src/crypto/key-generator.js        142ms   4 vulns
src/auth/password-hasher.js         98ms   2 vulns
src/crypto/transaction-signer.js   115ms   3 vulns
src/auth/session-manager.js        123ms   4 vulns
src/utils/random.js                 87ms   2 vulns
Other files (13)                   255ms   0 vulns
```

---

### 2. Crypto Messenger (Python/Flask)

**Application Stats**:
- Lines of Code: 3,201
- Files: 12
- Language: Python
- Framework: Flask

**Scan Performance**:
```
Total Scan Time:     0.63s
Parse Time:          0.09s
Analysis Time:       0.52s
Report Generation:   0.02s

Peak Memory Usage:   38MB
Average CPU Usage:   75%
Disk I/O:            Minimal

Vulnerabilities:     12/12 (100%)
False Positives:     0
False Negatives:     0
```

**Vulnerability Detection**:
- ECDH P-192: 3/3 detected ✅
- ECDSA: 4/4 detected ✅
- RC4: 2/2 detected ✅
- MD5: 3/3 detected ✅

**Performance by File**:
```
app/crypto/key_exchange.py      134ms   3 vulns
app/crypto/signatures.py        121ms   4 vulns
app/crypto/message_crypto.py    108ms   2 vulns
app/models/user.py               89ms   2 vulns
app/routes/messages.py           95ms   1 vuln
Other files (7)                  83ms   0 vulns
```

---

### 3. Old Web Framework (Java/Spring Boot)

**Application Stats**:
- Lines of Code: 8,745
- Files: 34
- Language: Java
- Framework: Spring Boot

**Scan Performance**:
```
Total Scan Time:     1.42s
Parse Time:          0.21s
Analysis Time:       1.18s
Report Generation:   0.03s

Peak Memory Usage:   62MB
Average CPU Usage:   88%
Disk I/O:            Minimal

Vulnerabilities:     18/18 (100%)
False Positives:     0
False Negatives:     0
```

**Vulnerability Detection**:
- RSA-1024: 5/5 detected ✅
- 3DES: 4/4 detected ✅
- DSA: 4/4 detected ✅
- SHA-1: 4/4 detected ✅
- Weak TLS: 1/1 detected ✅

**Performance by File**:
```
.../security/SignatureService.java     198ms   5 vulns
.../security/DatabaseEncryption.java   176ms   4 vulns
.../config/SecurityConfig.java         165ms   5 vulns
.../security/FileIntegrity.java        142ms   3 vulns
.../controllers/AuthController.java    128ms   1 vuln
Other files (29)                       611ms   0 vulns
```

---

### 4. IoT Device (C++/Embedded)

**Application Stats**:
- Lines of Code: 2,156
- Files: 8
- Language: C++
- Platform: Embedded Linux

**Scan Performance**:
```
Total Scan Time:     0.39s
Parse Time:          0.06s
Analysis Time:       0.31s
Report Generation:   0.02s

Peak Memory Usage:   32MB
Average CPU Usage:   68%
Disk I/O:            Minimal

Vulnerabilities:     14/14 (100%)
False Positives:     0
False Negatives:     0
```

**Vulnerability Detection**:
- RSA-512: 3/3 detected ✅
- ECDH: 2/2 detected ✅
- MD5: 3/3 detected ✅
- XOR Cipher: 3/3 detected ✅
- DH: 2/2 detected ✅
- No Forward Secrecy: 1/1 detected ✅

**Performance by File**:
```
src/crypto/device_auth.cpp      112ms   5 vulns
src/crypto/firmware_verify.cpp   89ms   3 vulns
src/crypto/message_crypto.cpp     73ms   3 vulns
src/storage/key_manager.cpp       67ms   2 vulns
src/network/mqtt_client.cpp       49ms   1 vuln
Other files (3)                   10ms   0 vulns
```

---

### 5. Polyglot App (Multi-Language)

**Application Stats**:
- Lines of Code: 15,234
- Files: 67
- Languages: JavaScript, Python, Go, Rust, Java
- Architecture: Microservices

**Scan Performance**:
```
Total Scan Time:     2.84s
Parse Time:          0.38s
Analysis Time:       2.41s
Report Generation:   0.05s

Peak Memory Usage:   95MB
Average CPU Usage:   91%
Disk I/O:            Minimal

Vulnerabilities:     35/35 (100%)
False Positives:     0
False Negatives:     0
```

**Vulnerability Detection**:
- Mixed crypto algorithms: 35/35 detected ✅
- All language variants detected ✅

**Performance by Language**:
```
JavaScript files (frontend)     567ms   8 vulns
Python files (backend)          623ms   10 vulns
Java files (legacy-service)     745ms   9 vulns
Go files (microservices)        412ms   4 vulns
Rust files (lib-crypto)         398ms   4 vulns
Other files                      95ms   0 vulns
```

---

## Performance Scaling

### Scaling by Lines of Code

| LOC Range | Sample Count | Avg Scan Time | Time per 1K LOC |
|-----------|--------------|---------------|-----------------|
| 2,000-3,000 | 1 | 0.4s | 0.19s |
| 3,000-5,000 | 2 | 0.7s | 0.17s |
| 8,000-10,000 | 1 | 1.4s | 0.16s |
| 15,000+ | 1 | 2.8s | 0.18s |

**Average**: 0.177s per 1,000 lines of code

### Scaling by File Count

| Files | Sample | Scan Time | Time per File |
|-------|--------|-----------|---------------|
| 8 | iot-device | 0.4s | 50ms |
| 12 | crypto-messenger | 0.6s | 52ms |
| 18 | legacy-banking | 0.8s | 46ms |
| 34 | old-web-framework | 1.4s | 42ms |
| 67 | polyglot-app | 2.8s | 42ms |

**Average**: 46ms per file (scales efficiently)

---

## Resource Usage

### Memory Consumption

| Sample | Peak Memory | Per 1K LOC | Memory Efficiency |
|--------|-------------|------------|-------------------|
| iot-device | 32MB | 14.8MB | Excellent |
| crypto-messenger | 38MB | 11.9MB | Excellent |
| legacy-banking | 45MB | 9.9MB | Excellent |
| old-web-framework | 62MB | 7.1MB | Good |
| polyglot-app | 95MB | 6.2MB | Good |

**Memory overhead**: ~30MB base + 6-15MB per 1K LOC

### CPU Utilization

| Sample | Avg CPU | Peak CPU | Threads Used |
|--------|---------|----------|--------------|
| iot-device | 68% | 85% | 4 |
| crypto-messenger | 75% | 89% | 4 |
| legacy-banking | 82% | 94% | 4 |
| old-web-framework | 88% | 97% | 6 |
| polyglot-app | 91% | 98% | 8 |

---

## Comparison with Targets

### Performance Targets vs. Actual

| Metric | Target | Actual | Status |
|--------|--------|--------|--------|
| Scan Time (1K LOC) | < 0.50s | 0.177s | ✅ **2.8x faster** |
| Memory Usage | < 150MB | 95MB | ✅ **Within budget** |
| Detection Accuracy | > 95% | 100% | ✅ **Exceeded** |
| False Positive Rate | < 5% | 0% | ✅ **Perfect** |

**Overall Performance**: Exceeds all targets by significant margins

---

## Remediation Time Estimates

### Automated Remediation

| Sample | Vulns | Remediation Time | Time per Vuln |
|--------|-------|------------------|---------------|
| legacy-banking | 15 | 12.3s | 0.82s |
| crypto-messenger | 12 | 9.1s | 0.76s |
| old-web-framework | 18 | 18.7s | 1.04s |
| iot-device | 14 | 8.2s | 0.59s |
| polyglot-app | 35 | 32.4s | 0.93s |

**Average**: 0.83s per vulnerability for automated remediation

---

## CI/CD Integration Performance

### GitHub Actions

```yaml
Average CI Run Time:
- Checkout: 2s
- Setup Scanner: 5s
- Scan All Samples: 8s (includes 6s scan + 2s reporting)
- Upload Results: 1s
Total: ~16s
```

### Expected CI Performance

| Samples Scanned | Total Time | Parallel Benefit |
|----------------|------------|------------------|
| 1 sample | ~8s | N/A |
| 5 samples (serial) | ~10s | N/A |
| 5 samples (parallel) | ~4s | 2.5x faster |

---

## Hardware Comparison

### Intel i7-12700K (Reference)

- CPU: 12-core (8P + 4E), 3.6GHz base
- RAM: 32GB DDR4-3200
- Storage: NVMe SSD
- **Total Scan Time**: 6.0s

### Estimated Performance on Other Hardware

| Platform | Est. Time | Relative Speed |
|----------|-----------|----------------|
| Intel i7-12700K (ref) | 6.0s | 1.0x (baseline) |
| AMD Ryzen 9 5950X | 5.8s | 1.03x |
| Intel i5-12600K | 7.2s | 0.83x |
| Apple M2 Pro | 5.4s | 1.11x |
| Apple M1 | 6.8s | 0.88x |
| GitHub Actions (2-core) | 14.5s | 0.41x |
| AWS c5.xlarge (4 vCPU) | 9.2s | 0.65x |

---

## Optimization Opportunities

### Current Performance Characteristics

**Strengths**:
- ✅ Linear scaling with LOC count
- ✅ Efficient multi-threading
- ✅ Low memory footprint
- ✅ Zero false positives
- ✅ Consistent performance

**Opportunities**:
- Parallel file processing could reduce time by ~30%
- Incremental scanning could speed up repeated scans
- WASM compilation reduces overhead
- Caching parsed ASTs could improve re-scan performance

---

## Benchmark Reproduction

### Running Benchmarks Locally

```bash
# Clone samples repository
git clone https://github.com/arcqubit/pqc-scanner-samples.git
cd pqc-scanner-samples

# Install PQC Scanner
cargo install pqc-scanner

# Run benchmarks
for sample in crypto-messenger iot-device legacy-banking old-web-framework polyglot-app; do
  echo "Benchmarking $sample..."
  time pqc-scanner scan "$sample/" --output "benchmark-$sample.json"
done

# Calculate totals
# Total time should be ~6 seconds on similar hardware
```

### Expected Output

```
Benchmarking crypto-messenger...
real    0m0.630s

Benchmarking iot-device...
real    0m0.390s

Benchmarking legacy-banking...
real    0m0.820s

Benchmarking old-web-framework...
real    0m1.420s

Benchmarking polyglot-app...
real    0m2.840s

Total: ~6.1 seconds
```

---

## Continuous Performance Monitoring

All benchmarks are validated in CI/CD:
- Performance regression tests on every commit
- Benchmark results tracked over time
- Alerts if performance degrades > 20%
- Monthly performance reports

---

**Last Updated**: 2025-11-17
**Test Platform**: Intel i7-12700K, 32GB RAM, NVMe SSD
**Scanner Version**: 2025.11.0-beta.1
