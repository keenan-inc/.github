# Applying the keenan-inc README template (mechanical)

For Claude Code, run per repo. Inputs you must resolve first: `{{REPO}}`, `{{PROJECT_NAME}}`, `{{ONE_LINER}}`, `{{PLATFORM}}`, `{{TECH}}`.

## Steps

1. Read the repo. Derive `{{INSTALL_COMMAND}}`, `{{SETUP_COMMAND}}`, `{{DEV_COMMAND}}`, `{{TEST_COMMAND}}`, `{{BUILD_COMMAND}}`, `{{RUNTIME_VERSIONS}}` from the real manifest (`package.json` scripts, `pyproject.toml`, `Cargo.toml`, `astro.config.*`). Never invent commands.
2. Copy `docs/README-TEMPLATE.md` from the `.github` repo to `README.md` in the target repo (preserve any hand-written prose from the old README by folding it into **What it is**).
3. `mkdir -p docs/assets`. Render the hero banner:
   - Fetch `banner/project-banner.template-dark.svg` and `-light.svg` from the brand assets path.
   - Replace `{{PROJECT_NAME}}` and `{{ONE_LINER}}` literally in each; save as `docs/assets/banner-dark.svg` / `banner-light.svg`.
4. Render the social card the same way from `social/project-social-preview.template-*.svg` (also replace `{{TECH}}` and `{{REPO}}`), save to `docs/assets/social-preview-{dark,light}.svg`, then export the **light** one to `docs/assets/social-preview.png` at exactly 1280×640 and upload it under Settings → Social preview.
5. Fill remaining `{{TOKENS}}`. Any token you cannot resolve from the repo becomes a `<!-- TODO: ... -->` comment — never a guess.
6. Ensure these exist, creating from org defaults if missing: `LICENSE`, `SECURITY.md`, `.github/workflows/ci.yml` (job id must be `ci` so the CI badge resolves).
7. Apply the label set: `gh label create` / `--force` for every row in `docs/LABELS.md` (or `gh api` from `labels.yml`).
8. Verify: no `{{` remains outside HTML comments; every image path resolves; badge row renders in both color schemes.

## Invariants

- Section order is fixed: What it is → Screenshots → Install → Development → Architecture → Security → License.
- Badge style is always `flat-square` with `labelColor=21262D` and `color=0F6E63`. No other styles, no gradients, no emoji.
- Every image is inside a `<picture>` with dark + light sources.
- Brand assets are referenced from stable raw paths in the `.github` repo; never vendor a copy of the logo into a project repo.
