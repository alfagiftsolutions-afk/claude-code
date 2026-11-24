# active-memory handoff: Gift On Demand Shopify redesign & SEO

**Handoff #1** · 2026-11-24 · Lineage: #1 (2026-11-24): niche + printmine.in research, Bold redesign, logo-preview tool, homepage SEO, audit with GSC data, collection SEO fixes; publish of last theme fixes blocked by settings_data conflict.

## 0. Instructions for Claude (read first)

You are continuing work from a previous chat. That chat is gone; this file is the complete context and the source of truth.

1. Read this whole file before replying.
2. Follow sections 3 (Style), 4 (Hard rules) and 5 (Corrections) in every reply, for the rest of this chat. They override your defaults.
3. Use the values in section 8 exactly. Never round, re-estimate, or "correct" them.
4. Do not suggest anything listed in section 7 (Changed / rejected) again unless the user brings it up.
5. Code word: None active. If the user types /amcodeword, start every reply with the phrase they choose (default "Yes Boss!").
6. Your first reply: at most 5 lines covering the goal, the current state, and the next step (section 11). Mention any files from section 13 that were not attached. Ask the questions in section 12 if there are any. End with "Ready to continue with <next step>?" Then wait for the user's go.

## 1. Mission
- **Goal:** Rebuild/upgrade the Shopify store giftondemand.in so it looks better and more trustworthy than competitor printmine.in, has its key features, and ranks on Google's first page.
- **Done looks like:** Attractive desktop + mobile site (mobile already approved), competitor features live, SEO fixes published, non-brand Google rankings improving.
- **Why it matters:** User's stated aim: "my aim is to be on top of atleast in the first page of Google search".

## 2. About the user (as relevant to this work)
- Owner of Gift On Demand (operated by Alfa Gift Solutions, Jhandewalan Extension, Karol Bagh, New Delhi 110005). Sells logo-branded corporate gifts in India (INR), Shopify Basic plan.
- Non-technical; reviews on phone (Android Chrome) and desktop; owns Kalles theme (said "kallas 5.5", later "kalles 2.5"; store runs Kalles 2.5.0).
- Store connected via Shopify MCP; Google Search Console property `https://www.giftondemand.in/` connected via Advanced GSC (free plan limits).

## 3. Style & communication
- **Language:** English.
- **Tone:** direct, plain, non-technical; explain impact, not code.
- **Reply length:** concise; summaries with clear sections; offer next step.
- **Formatting:** short headings, bullets, tables OK; plain words for the user.
- **Working style:** audit/research first, then act; show screenshots-verified results; confirm before publishing; use skills when relevant (user asked "use skills").
- **Avoid:** plain/empty "minimal" designs; unverified claims; publishing without explicit yes.

## 4. Hard rules (word for word)
1. "AUDIT THE WEBSITE FIRST" (before making further changes).
2. "First save it in Shopify draft so I can view it" (work on an unpublished/draft theme, let user preview).
3. "Make it seo centric because my aim is to be on top of atleast in the first page of Google search".
4. "use skills" (load relevant skills for design/SEO work).
5. Never call theme_publish without the user's explicit yes naming the theme (user gave "YES PUBLISH" for theme 190542250236 on 2026-11-24).
6. Never invent reviews, client logos, order counts, certifications or prices; every claim must come from the store's own pages/policies or live data.

## 5. Corrections log
| # | Claude did | The user wanted |
|---|---|---|
| 1 | Built "Boardroom Minimal" white/serif design | "No I don't like the website" — too plain/empty, not enough products, not trustworthy, wrong fonts → research printmine.in, bold & colourful |
| 2 | Desktop layout after Bold redesign | "desktop version of it does not look that much promising make it more attractive" (mobile approved: "Mobile site looks good") |
| 3 | Saved new homepage sections in same commit as settings_data with >25 sections; verified only via pending-edit screenshots | User saw homepage starting at bulk-quote ("Website starts from here"). Keep ≤25 sections, unique block IDs, verify saved file via GraphQL after commit |
| 4 | Duplicated live theme expecting committed-unpublished edits to copy | themeDuplicate copies only published state; re-apply edits to copy |
| 5 | Was about to make more SEO changes | User: "AUDIT THE WEBSITE FIRST" |

## 6. Decisions
| Decision | Why |
|---|---|
| Bold & colourful direction (Bricolage Grotesque + Figtree, orange/ink palette) | User's choice over Premium dark / Clean marketplace |
| Build own gx-* sections instead of restyling Kalles sections | Kalles lazysizes images render as placeholders; own sections reliable |
| Reviews/ratings read live from Judge.me metafields; no "Verified" label | Real data; verified_buyer=false on all reviews |
| Logo preview tool client-side; logo handed to product page upload via sessionStorage + DataTransfer | No backend; upload field is app-rendered (King Product Options) |
| WhatsApp 919717801827 from contact page | No WhatsApp number in theme (flagged; user never contradicted) |
| Fill empty occasion collections with fitting personalised products instead of unpublishing | They get search impressions; content better than 404 |
| Publish everything incl. other process's SEO tweaks | User: "YES PUBLISH" |

## 7. Changed / rejected
- "Boardroom Minimal" (Fraunces/Manrope, ink + green #0B6B4F) → "Bold & Bright" (user disliked minimal).
- Homepage title 'Corporate & Promotional Gifts in India | Gift On Demand' → 'Corporate Gifts with Logo in India | Gift On Demand'.
- Corporate-gifts collection title "Corporate Gifts" → "Bulk Corporate Gifts for Employees & Clients".
- ❌ Premium dark / Clean marketplace directions (not chosen).
- ❌ Copying printmine's design/assets (only features/patterns, original design).
- Hero subheading "…Order from just 2 pieces." → other process's "…T-shirts from 2 pieces, most gifts from 5." (queued, not live yet).

## 8. Data & facts (exact)
- Shop: Gift On Demand, www.giftondemand.in, order@giftondemand.in, +91 97178 01827, GSTIN 07BRCPA3679P1ZD, INR, Shopify Basic.
- Policies: custom production 2–4 business days after artwork approval; delivery metro 3–5, rest of India 5–7, remote 7–10 business days after dispatch; free shipping prepaid orders above ₹1,500; partial COD advance 30–50%; damage report within 48 hours with unboxing proof; refunds 7–10 business days; customized items cancel only before production.
- MOQ: polos/round-neck tees 2 pcs; gift kits 3 sets; many gift sets & bottles 5; pens & totes 10; pop sockets 50.
- Bulk discounts: 5% (10–49), 10% (50–99), 15% (100+), automatic.
- Judge.me: 4.72 average, 882 reviews.
- GSC (90 days to 2026-11-24): 229 clicks, 10,761 impressions, CTR 2.13%, avg position 22.9. /collections/corporate-gifts: 1,152 impressions, avg pos 59.6. Brand query "gift on demand" 32 clicks pos 2.3.
- Core Web Vitals (CrUX origin): LCP 2119 ms good, INP 198 ms good, CLS 0.12 needs improvement (FAILED).
- Themes: LIVE = 190542250236 "Boardroom Minimal - Draft - 24 Nov 2026" (published by user 2026-11-23 23:16Z). Previous: 190539989244 "SEO GEO AEO - 24 Nov 2026" (unpublished).
- Colours (settings): cl_hd #15110E, cl_bd_text #4D4743, color_primary #C93A0A, bgatc_pg_hover #A12E07, god_brand_peach #FFE4D4, god_brand_copper #FF6B2C, god_brand_surface #FFF7F2, god_brand_border #F1E2D8, god_brand_control #6F6762. Fonts: fnt_heading2 "Bricolage Grotesque", fnt_bd2/fnt_sub_tt2 "Figtree".
- Collection IDs: corporate-gifts 473233752316, wedding-engagement 472480874748, baby-shower-new-born 472480907516, valentines-day 472480940284, rakhi-raksha-bandhan 472480973052, customize-pens 473233948924.

## 9. People, terms & names
- **People:** Harsh Vardhan Agrawal = founder of competitor PrintMine.in (Raipur).
- **Terms:** gx- = Bold design code; bm- = older Boardroom code; "other process" = unknown tool/session that commits to the live theme (price-index script `npm run seo:price-index`, social-meta-tags, agents.md, product.liquid).
- **Names in use:** sections gx-hero, gx-products, gx-preview, gx-cats, gx-reviews, gx-why, gx-story, gx-seo, bm-quote, bm-faq; snippets gx-card, gx-whatsapp, bm-tokens, bm-trust-box; assets gx-bold.css, gx-preview.js, gx-handoff.js; DESIGN.md in theme root.

## 10. Work state
| Item | Status | Version / location | Notes |
|---|---|---|---|
| Bold redesign + homepage SEO (H1, FAQ schema, gx-seo link hub, meta) | LIVE | theme 190542250236 | verified |
| Collection SEO (corporate-gifts title/H1/copy; 4 occasion collections filled + copy; pens 1→6) | LIVE (store data) | Shopify admin | done 2026-11-24 |
| Theme fixes: pr_loop_list clean /products/ URLs, homepage-approved.css removed, Judge.me CLS guards | Committed, NOT published | theme 190542250236 | theme_publish rejectedReason "changed_on_shopify" on config/settings_data.json |
| Hero btn1 "Shop corporate gifts" → /collections/corporate-gifts; btn2 "Preview your logo free" | To re-apply | settings_data gx_hero | reverted to match live to try clear conflict |
| Other process's tweaks: hero subheading "Branded gifts for teams and clients, printed in Delhi and shipped across India. T-shirts from 2 pieces, most gifts from 5."; gx_why w3 title "Low minimum quantities" | To re-apply | settings_data | |
| Handoff notes | committed | repo branch claude/chat-session-jr9gia, .handoff/ | |

## 11. Next steps
1. **Next action:** Ask the user whether another tool/Claude session writes to the live theme; once it is paused/finished, retry theme_publish on 190542250236 (with user's existing "YES PUBLISH").
2. After publish succeeds, re-apply the four settings edits in section 10 (separate commit; settings_data only), then publish again (confirm with user).
3. Optional follow-ups: tune logo-preview positions (cap/bottle/notebook), plain product mockups, real team/founder photo for gx_story, remove Shopify Inbox overlap, verify "Trusted by 58000+ brands" product-page image claim, check CLS in CrUX after ~28 days.

## 12. Open questions ⚠️
- Is another tool or Claude session writing to the live theme? (yes → pause/let it publish first / no → retry later)
- Confirm WhatsApp number 919717801827 is correct for WhatsApp.

## 13. Re-attach checklist
- Nothing to attach. (Theme lives in Shopify; earlier context also in repo `.handoff/handoff.md`.)

---
<sub>Audit: 13/13 sections · 6 rules · 5 corrections · 40 data points · secrets removed: none found · generated by active-memory</sub>
