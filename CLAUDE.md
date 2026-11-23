# CLAUDE.md

Guidance for Claude Code and other coding agents working in this repository.

## Security hardening for GitHub Actions

Workflow jobs in this repository that call Claude run with three protections.
Keep them when you add or edit a workflow.

1. **Egress-firewall runner.** The job has `runs-on: ubuntu-24.04-firewall`,
   a GitHub-hosted runner that filters the job's outbound network traffic. Do
   not move a job that calls Claude to another runner.
2. **Network allow list.** `.github/egress-firewall.yaml` lists the hosts
   those jobs may reach, besides any that GitHub's firewall allows by default.
   Keep `mode: enforce`, which is what makes the firewall block the rest. Follow
   that file's header when you add a host.
3. **Auto permission mode.** Every step that runs the Claude Code action
   (`uses: anthropics/claude-code-action`, or a local action with a
   `claude_args` input) passes `--permission-mode auto` in `claude_args`. A tool
   call that needs permission and that the allowed tools do not cover then runs
   only if Claude Code's safety review passes it. Allow only the tools the job
   needs, and keep any `--disallowedTools` list a step has. Use `claude-opus-4-6`
   or a newer model: on an older one Claude Code falls back to its default
   permission mode.

`claude.yml` answers `@claude` mentions. The Claude Code action sets
`--permission-mode acceptEdits` for those, and the `--permission-mode auto` in
the workflow's `claude_args`, which comes after it, replaces it.

`.github/workflows/workflow-hardening.yml` fails when a job that runs the Claude
Code action or mentions `ANTHROPIC_FEDERATION_RULE_ID` breaks protection 1 or 3,
or when the allow list is missing, empty, not `mode: enforce`, or names a host
with `*`. It cannot see a job that calls Claude another way, so check new
workflows by hand too. If a job cannot meet protection 1 or 3, add it with the
reason to the matching exemption table in
`.github/scripts/check_workflow_hardening.py`. A job in `EXEMPT_FROM_AUTO_MODE`
must set no permission mode at all. Do not skip or weaken the check.

Keep each workflow's `permissions:` block minimal, and never print tokens or
environment variables in workflow logs.

<!-- handoff:learnings:begin -->
## Session Learnings (auto-updated by handoff)

### Implicit Rules
- Store: Gift On Demand, Shopify Basic, INR, Kalles 2.5 vintage (no JSON templates; homepage via settings_data content_for_index)
- Edit theme only via Shopify MCP theme_bash/theme_commit/theme_screenshot; theme_screenshot shows pending edits, not saved state
- settings_data.json has /* */ header — strip with sed before jq, or use jq --jsonc
- Product MOQ in metafield custom.minimum_order_quantity (list, use .value.first); Judge.me ratings in reviews.rating / reviews.rating_count
- Never publish (theme_publish) without explicit user approval naming the theme
- Prefix new code gx- (Bold) / bm- (Boardroom); keep copy editable in section settings

### Key Decisions
- Decision: work only on duplicate draft theme, never publish without explicit user yes — Reason: live store must stay unchanged during review
- Decision: build new gx-* sections instead of restyling Kalles sections — Reason: Kalles lazysizes images render as placeholders and markup is hard to control; own sections use image_tag and load reliably
- Decision: every trust claim sourced from store's own pages (FAQ, shipping, refund, about) or live data — Reason: avoid fabricated claims; GSTIN 07BRCPA3679P1ZD, free shipping prepaid >₹1,500, 2–4 day production, MOQ from 2, partial COD 30–50%, 48h damage window
- Decision: reviews/ratings read live from Judge.me shop metafields (all_reviews_rating, all_reviews_count, reviews_grid) and product reviews.rating — Reason: real data, auto-updates; no 'Verified' label because verified_buyer=false
- Decision: logo preview fully client-side, sessionStorage handoff to PDP file input via DataTransfer — Reason: no backend; PDP upload field is app-rendered so attach by polling
- Decision: colours via existing god_brand_* + cl_hd/color_primary settings, fonts via fnt_heading2/fnt_bd2 Google Fonts path — Reason: settings-driven, merchant-editable; no new font provider
- Decision: WhatsApp number 919717801827 taken from contact page phone — Reason: no WhatsApp number in theme; flagged to user for confirmation

<!-- handoff:learnings:end -->
