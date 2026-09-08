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

## Why this stack

The standard path was chosen for AlgoTree, which is a web-app with an MVP budget of 3 weeks. `10x-astro-starter` is the vetted, agent-friendly recommendation for JS/TS web applications. It provides authentication (Supabase), a database, and an edge deployment target (Cloudflare Pages) out of the box, aligning perfectly with the auth requirements and AI-quiz generation logic found in the PRD. The chosen deployment target, CI/CD provider (GitHub Actions), and deployment flow (auto-deploy on merge) all use the recommended defaults, allowing the solo developer to maximize speed of iteration.
