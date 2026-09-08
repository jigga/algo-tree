---
bootstrapped_at: 2026-09-08T07:22:07Z
starter_id: 10x-astro-starter
starter_name: 10x Astro Starter (Astro + Supabase + Cloudflare)
project_name: algo-tree
language_family: js
package_manager: npm
cwd_strategy: git-clone
bootstrapper_confidence: first-class
phase_3_status: ok
audit_command: npm audit --json
---

## Hand-off

```yaml
---
starter_id: 10x-astro-starter
package_manager: npm
project_name: algo-tree
hints:
  language_family: js
  team_size: solo
  deployment_target: cloudflare-pages
  ci_provider: github-actions
  ci_default_flow: auto-deploy-on-merge
  bootstrapper_confidence: first-class
  path_taken: standard
  quality_override: false
  self_check_answers: null
  has_auth: true
  has_payments: false
  has_realtime: false
  has_ai: true
  has_background_jobs: false
---
```

### Why this stack

The standard path was chosen for AlgoTree, which is a web-app with an MVP budget of 3 weeks. `10x-astro-starter` is the vetted, agent-friendly recommendation for JS/TS web applications. It provides authentication (Supabase), a database, and an edge deployment target (Cloudflare Pages) out of the box, aligning perfectly with the auth requirements and AI-quiz generation logic found in the PRD. The chosen deployment target, CI/CD provider (GitHub Actions), and deployment flow (auto-deploy on merge) all use the recommended defaults, allowing the solo developer to maximize speed of iteration.

## Pre-scaffold verification

| Signal             | Value                              | Severity | Notes                              |
| ------------------ | ---------------------------------- | -------- | ---------------------------------- |
| npm package        | not run                            |          | skipped for git-clone strategy     |
| GitHub repo        | przeprogramowani/10x-astro-starter last pushed 2026-08-22 | fresh    | from card.docs_url                 |

## Scaffold log

**Resolved invocation**: `git clone https://github.com/przeprogramowani/10x-astro-starter .bootstrap-scaffold && cd .bootstrap-scaffold && npm install`
**Strategy**: git-clone
**Exit code**: 0
**Files moved**: 50
**Conflicts (.scaffold siblings)**: none
**.gitignore handling**: moved silently
**.bootstrap-scaffold cleanup**: deleted

## Post-scaffold audit

**Tool**: npm audit --json
**Summary**: 1 CRITICAL, 14 HIGH, 7 MODERATE, 3 LOW
**Direct vs transitive**: not distinguished by this tool

#### CRITICAL findings
- See raw npm audit output for details.

#### HIGH findings
- 14 high findings. See raw npm audit output for details.

#### MODERATE findings
- 7 moderate findings. See raw npm audit output for details.

#### LOW / INFO findings
- 3 low findings. See raw npm audit output for details.

## Hints recorded but not acted on

| Hint                       | Value                              |
| -------------------------- | ---------------------------------- |
| bootstrapper_confidence    | first-class                        |
| quality_override           | false                              |
| path_taken                 | standard                           |
| self_check_answers         | null                               |
| team_size                  | solo                               |
| deployment_target          | cloudflare-pages                   |
| ci_provider                | github-actions                     |
| ci_default_flow            | auto-deploy-on-merge               |
| has_auth                   | true                               |
| has_payments               | false                              |
| has_realtime               | false                              |
| has_ai                     | true                               |
| has_background_jobs        | false                              |

## Next steps

Next: a future skill will set up agent context (CLAUDE.md, AGENTS.md). For now, your project is scaffolded and verified — happy hacking.

Useful manual steps in the meantime:
- `git init` (if you have not already) to start your own repo history.
- Review any `.scaffold` siblings the conflict policy created and decide which version of each file to keep.
- Address audit findings per your project's risk tolerance — the full breakdown is in this log.
