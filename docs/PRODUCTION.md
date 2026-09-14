# Production Checklist

## Deployment

- [x] GitHub repository connected
- [x] Static Netlify publish directory configured
- [x] Production response headers configured
- [x] Original source preserved
- [x] Responsive coarse-pointer fallback added
- [x] Witness console output escaped before HTML insertion

## Runtime verification

- [ ] Verify `/demo/status` from the production browser
- [ ] Verify `POST /demo/chat`
- [ ] Verify GitHub tree/file fetch
- [ ] Verify all CDN dependencies load
- [ ] Verify no console errors
- [ ] Verify mobile navigation and controls
- [ ] Verify ledger export/import
- [ ] Verify ledger tamper detection

## Truth classification

### Real browser behavior

- SHA-256 ledger sealing uses Web Crypto.
- Ledger tamper detection recomputes hashes in the browser.
- GitHub repository browsing uses the GitHub REST API.
- The witness console calls the configured demo API when available.

### Demonstration behavior

- API Console endpoints are MSW/demo concepts.
- Drift chart values are generated client-side.
- Terminal ambient logs are presentation telemetry.
- Migration and ritual sequences are interactive demonstrations.

## Security

- Never place API keys, JWT secrets, database credentials or private tokens in `index.html`.
- Escape user/API text before inserting it into HTML.
- Keep third-party CDN dependencies pinned.
- Review CORS and endpoint rate limits on the backend before calling an integration production-grade.
