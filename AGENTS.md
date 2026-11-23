# AGENTS.md

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
