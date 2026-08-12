# keenan-inc issue label palette

One set across every repo. Namespaced with `/` so GitHub groups them and filters read cleanly (`label:type/bug label:priority/p1`). Colors come from the brand tokens — priority runs risk→warn→gray, status runs cool→accent.

| Label | Hex | Description |
| :--- | :--- | :--- |
| `type/feature` | `#0F6E63` | New capability or enhancement |
| `type/bug` | `#C4534B` | Defect in existing behavior |
| `type/security` | `#8C2B24` | Security defect, hardening, or dependency risk |
| `type/docs` | `#6E7681` | Documentation, README, or comments |
| `type/refactor` | `#30363D` | Internal change with no behavior change |
| `type/build` | `#21262D` | Build, CI, packaging, or release tooling |
| `type/question` | `#7D6BB0` | Clarification or discussion needed |
| `priority/p0` | `#8C2B24` | Drop everything — broken, unsafe, or shipping-blocking |
| `priority/p1` | `#C4534B` | Next up — needed for the current milestone |
| `priority/p2` | `#C9A227` | Planned — scheduled but not urgent |
| `priority/p3` | `#6E7681` | Someday — nice to have, no commitment |
| `status/triage` | `#C9D1D9` | Not yet assessed |
| `status/accepted` | `#0F6E63` | Assessed and queued for work |
| `status/in-progress` | `#2FA694` | Actively being worked |
| `status/blocked` | `#C4534B` | Waiting on a dependency, decision, or upstream fix |
| `status/needs-info` | `#C9A227` | Waiting on the reporter |
| `status/wont-do` | `#30363D` | Deliberately declined — closes with a reason |
| `security` | `#8C2B24` | Touches a trust boundary, auth, crypto, or data handling — requires review before merge |
| `good-first-issue` | `#2FA694` | Small, well-scoped, safe entry point |
| `dependencies` | `#7D6BB0` | Dependency updates and audit findings |

Apply with:

```bash
gh label list --json name -q '.[].name' | xargs -I{} gh label delete {} --yes   # optional: clear defaults
gh label create "type/feature" --color 0F6E63 --description "New capability or enhancement" --force
gh label create "type/bug" --color C4534B --description "Defect in existing behavior" --force
gh label create "type/security" --color 8C2B24 --description "Security defect, hardening, or dependency risk" --force
gh label create "type/docs" --color 6E7681 --description "Documentation, README, or comments" --force
gh label create "type/refactor" --color 30363D --description "Internal change with no behavior change" --force
gh label create "type/build" --color 21262D --description "Build, CI, packaging, or release tooling" --force
gh label create "type/question" --color 7D6BB0 --description "Clarification or discussion needed" --force
gh label create "priority/p0" --color 8C2B24 --description "Drop everything — broken, unsafe, or shipping-blocking" --force
gh label create "priority/p1" --color C4534B --description "Next up — needed for the current milestone" --force
gh label create "priority/p2" --color C9A227 --description "Planned — scheduled but not urgent" --force
gh label create "priority/p3" --color 6E7681 --description "Someday — nice to have, no commitment" --force
gh label create "status/triage" --color C9D1D9 --description "Not yet assessed" --force
gh label create "status/accepted" --color 0F6E63 --description "Assessed and queued for work" --force
gh label create "status/in-progress" --color 2FA694 --description "Actively being worked" --force
gh label create "status/blocked" --color C4534B --description "Waiting on a dependency, decision, or upstream fix" --force
gh label create "status/needs-info" --color C9A227 --description "Waiting on the reporter" --force
gh label create "status/wont-do" --color 30363D --description "Deliberately declined — closes with a reason" --force
gh label create "security" --color 8C2B24 --description "Touches a trust boundary, auth, crypto, or data handling — requires review before merge" --force
gh label create "good-first-issue" --color 2FA694 --description "Small, well-scoped, safe entry point" --force
gh label create "dependencies" --color 7D6BB0 --description "Dependency updates and audit findings" --force
```

Conventions: exactly one `type/*` and one `priority/*` per issue; `status/*` reflects the present moment and changes over the issue's life; the bare `security` label is additive — it flags review requirements and can sit alongside `type/feature`.
