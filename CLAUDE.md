# God's Eye View — notes for this copy

**Repo:** `aegis-intel-ops/gods-eye-view` (public) · branch `main`

A copy of Bilawal Sidhu's open-source God's Eye View: a browser-based 3D globe (Vite + vanilla
JS, CesiumJS / Google 3D tiles) with live aircraft, ships, satellites, earthquakes, traffic and
public cameras, plus realtime voice control. All commits are upstream authors — this is not
Aegis-authored code. Keep local changes minimal, and prefer syncing from upstream to diverging.

**Read:** `README.md`, `CONTRIBUTING.md`, `TESTING.md` (manual field-test script),
`DATA_SOURCES.md`, `SECURITY.md`, `config/`, `docs/`.

## Commands
```bash
PUPPETEER_SKIP_DOWNLOAD=1 npm ci   # skip only if Chrome can't be downloaded (sandbox/CI)
npm run doctor -- --json           # setup policy checks
npm test                           # node --test unit suite (~2,700 tests)
npm run test:track                 # tracking-invariant regression
npm run build                      # vite production bundle
npm run dev
```
`package.json` declares Node >=24.14 <25 or 26.x (the suite also passed on Node 22).
Headless QA harnesses live in `scripts/qa-*.mjs` (need puppeteer's Chrome).

## Notes
- Tests are colocated as `src/**/*.test.mjs`.
- API keys are optional and entered in-app (`keySetup*`); never commit a filled `.env`.
