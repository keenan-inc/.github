<!--
  keenan-inc repo README template — v1.0
  Replace every {{TOKEN}}. Delete sections that genuinely do not apply; do not reorder them.
-->

<p align="center">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="docs/assets/banner-dark.svg">
    <source media="(prefers-color-scheme: light)" srcset="docs/assets/banner-light.svg">
    <img alt="{{PROJECT_NAME}}" width="880" src="docs/assets/banner-light.svg">
  </picture>
</p>

<p align="center"><strong>{{ONE_LINER}}</strong></p>

<p align="center">
  <a href="https://github.com/keenan-inc/{{REPO}}/actions/workflows/ci.yml"><img alt="CI" src="https://img.shields.io/github/actions/workflow/status/keenan-inc/{{REPO}}/ci.yml?style=flat-square&labelColor=21262D&color=0F6E63&label=ci"></a>
  <a href="https://github.com/keenan-inc/{{REPO}}/releases"><img alt="Version" src="https://img.shields.io/github/v/release/keenan-inc/{{REPO}}?style=flat-square&labelColor=21262D&color=0F6E63&label=version&display_name=tag&sort=semver"></a>
  <a href="LICENSE"><img alt="License" src="https://img.shields.io/github/license/keenan-inc/{{REPO}}?style=flat-square&labelColor=21262D&color=0F6E63&label=license"></a>
  <img alt="Platform" src="https://img.shields.io/badge/platform-{{PLATFORM}}-0F6E63?style=flat-square&labelColor=21262D">
</p>

---

## What it is

{{TWO_TO_FOUR_SENTENCES}} — what problem it solves, who it is for, and what it deliberately does **not** do.

## Screenshots

<p align="center">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="docs/assets/screenshot-main-dark.png">
    <source media="(prefers-color-scheme: light)" srcset="docs/assets/screenshot-main-light.png">
    <img alt="{{PROJECT_NAME}} main window" width="880" src="docs/assets/screenshot-main-light.png">
  </picture>
</p>

## Install

```bash
{{INSTALL_COMMAND}}
```

Signed builds for macOS, Windows and Linux are on the [releases page]( https://github.com/keenan-inc/{{REPO}}/releases). Verify checksums before running:

```bash
shasum -a 256 -c SHA256SUMS
```

## Development

**Requirements:** {{RUNTIME_VERSIONS}}

```bash
git clone https://github.com/keenan-inc/{{REPO}}.git
cd {{REPO}}
{{SETUP_COMMAND}}
{{DEV_COMMAND}}     # run locally
{{TEST_COMMAND}}    # tests
{{BUILD_COMMAND}}   # production build
```

## Architecture

| Layer | Responsibility | Lives in |
| :--- | :--- | :--- |
| {{LAYER}} | {{RESPONSIBILITY}} | `{{PATH}}` |

{{ONE_PARAGRAPH_ON_DATA_FLOW_AND_TRUST_BOUNDARIES}}

## Security

- **Data handling:** {{WHERE_DATA_LIVES}} — local-first, no telemetry unless explicitly stated.
- **Trust boundaries:** {{IPC_NETWORK_FS_BOUNDARIES}}
- **Dependencies:** audited in CI ({{AUDIT_TOOL}}); Dependabot enabled.
- **Reporting a vulnerability:** see [SECURITY.md](SECURITY.md). Do not open a public issue for a security defect.

## License

{{LICENSE_NAME}} — see [LICENSE](LICENSE).

<br>

<p align="center">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/keenan-inc/.github/main/assets/brand/logo/mark-dark.svg">
    <source media="(prefers-color-scheme: light)" srcset="https://raw.githubusercontent.com/keenan-inc/.github/main/assets/brand/logo/mark-light.svg">
    <img alt="keenan-inc" width="20" src="https://raw.githubusercontent.com/keenan-inc/.github/main/assets/brand/logo/mark-light.svg">
  </picture>
</p>
<p align="center"><sub>Built by <a href="https://github.com/keenan-inc"><b>keenan-inc</b></a> — security-minded software, built small and shipped finished.</sub></p>
