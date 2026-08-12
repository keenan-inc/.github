# .github — org defaults for keenan-inc

- `profile/README.md` — the public org profile page
- `.github/workflows/` — reusable CI workflows (`workflow_call`) shared by all fleet repos
- `renovate-config/default.json` — org-wide Renovate preset

Projects consume the shared CI with a ~10-line caller workflow and extend the
Renovate preset from their `renovate.json`. Improve the pipeline here once;
every repo inherits it.
