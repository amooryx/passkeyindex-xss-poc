# passkeyindex.io stored-XSS PoC

This public page is a static build of itwarden/passkeys-index with one malicious README row added:

``markdown
| ![logo](/public/logos/0pass.svg) | <img src=x onerror="alert(document.domain)"> | [poc.example](https://example.com/) | ![Login](/public/tags/login.svg "Login") |
``

The upstream README is parsed by marked and rendered with Astro set:html; raw HTML in the README is not sanitized. This build demonstrates that a merged README contribution executes JavaScript on the deployed site.

This is an authorized security PoC; it does not modify the upstream repository.
