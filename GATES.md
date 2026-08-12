# Gates

Required status checks on every PR into `main` (org-wide ruleset — see
below). Job IDs are fixed by the org ruleset; don't rename them.

| Job ID | Workflow | What it checks |
| :--- | :--- | :--- |
| `gates` | `ci.yml` | Aggregator — fails if any lint/test job it depends on fails, is cancelled, or is skipped |
| `secret-scan` | `security.yml` | TruffleHog scan of full git history for verified/unknown secrets |
| `dependency-audit` | `security.yml` | No-op here — no dependency manifests in this repo, but the check must stay green |

Run locally before pushing:

```bash
# labels.yml
python3 -c "import yaml; d=yaml.safe_load(open('labels.yml')); assert all('name' in e and 'color' in e for e in d); print('OK')"

# renovate-config/*.json
python3 -c "import glob,json; [json.load(open(p)) for p in glob.glob('renovate-config/*.json')]; print('OK')"
```

## GitHub-side controls

Enforced at the org level, not in this repo's files:

- **Org ruleset — baseline protection**: applies to every repo in
  `keenan-inc`. Blocks force-pushes and branch deletion on `main`, requires
  a pull request before merging.
- **Org ruleset — PR gates**: requires the `gates`, `secret-scan`, and
  `dependency-audit` status checks (by job ID) to pass before a PR into
  `main` can merge, in every repo.
- **Native secret scanning**: enabled on this repo (it's public, so GitHub
  provides this at no cost) as a second, independent layer on top of the
  `secret-scan` CI gate above.
