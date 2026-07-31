# CyberTool Suite

A dependency-free, browser-only security utility toolkit. Everything runs client-side via the Web Crypto API — no backend, no build step, no data ever leaves the browser.

**[Live tools →](#)** *(replace with your GitHub Pages link once deployed — see below)*

## Tools included

- **Hash Generator** — live MD5, SHA-1, SHA-256, and SHA-512 digests of any text input
- **Password Strength Analyzer** — entropy-based scoring, pattern/common-password checks, and estimated offline brute-force time
- **Encode / Decode** — Base64, URL, and Hex, either direction
- **JWT Decoder** — inspect a token's header and payload, with flags for `alg: none`, expired tokens, and missing `exp` claims

## Why it's built this way

- **Zero dependencies.** Everything is vanilla HTML/CSS/JS in a single file. No `npm install`, no CDN calls, nothing to audit but the code itself.
- **Nothing is transmitted.** Hashing uses the browser's native [SubtleCrypto](https://developer.mozilla.org/en-US/docs/Web/API/SubtleCrypto) API; MD5 (not available natively) is implemented directly in JS. Password strength analysis and JWT decoding are pure local string/JSON parsing.
- **Decoding ≠ verifying.** The JWT tool deliberately does not attempt signature verification — it's a readability and awareness tool, not an auth library.

## Running locally

No build step required.

```bash
git clone https://github.com/<your-username>/cybertool-suite.git
cd cybertool-suite
python3 -m http.server 8000
# open http://localhost:8000
```

Or just open `index.html` directly in a browser.

## Deploying to GitHub Pages

1. Push this repo to GitHub.
2. Go to **Settings → Pages**.
3. Set **Source** to the `main` branch, root directory.
4. Your suite will be live at `https://<your-username>.github.io/cybertool-suite/`.

## Disclaimer

MD5 and SHA-1 are included for legacy/interoperability reference only. Both are cryptographically broken and unsuitable for password hashing or integrity guarantees — use SHA-256/SHA-512, or better, a purpose-built password hash like bcrypt/argon2 server-side.

## License

MIT — see [LICENSE](LICENSE).
