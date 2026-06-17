# StatsDeck site — handoff to Claude Code

Static landing site for **statsdeck.ai** (Cloudflare Pages, apex). Light theme.
MCP server stays on Railway at the `mcp.` subdomain.

## Files
- `public/index.html` — landing page (single page, light background)
- `public/privacy.html` — privacy policy (DRAFT — have it reviewed before publish)

## TO DO before deploy

### 1. Logo  ← DONE (already in package)
`public/logo.png` is your SD-LOGO with the white background knocked out to transparent,
so it sits cleanly on the cream page. It appears in the top bar (42px), a prominent
centered hero logo (96px), and the footer (30px) — all from the one file. A styled
"StatsDeck" wordmark is the automatic fallback if the file is ever missing.

If you'd rather use a crisper SVG export from the PSD, just drop it in as `public/logo.svg`
and change the three `src="/logo.png"` references. Still copy
`Favicon-512-StatsDeck` → `public/favicon-512.png` (already referenced).

NOTE on accents: the page palette is now drawn from the logo — blue #2693BE (primary:
buttons, links, "actually right"), gold #FFCA08 (secondary highlight), charcoal #34373E
(text). The comparison block keeps green/amber ONLY as correct-vs-off signals, since
that semantic coding is what makes that section readable at a glance.

### 2. Screenshots
8 styled placeholders (4 product + 4 install). Replace each `<div class="shot-img">`
and `<div class="step-shot">` with a real `<img src="/img/..." alt="...">`.

### 3. Confirm the install URL
Install section uses `https://mcp.statsdeck.ai/mcp`. Confirm it matches the final
Railway custom-domain subdomain before publishing.

### 4. Privacy policy
`privacy.html` is a starting draft, not legal advice. Set the date, confirm every
line matches actual server behavior, and get it reviewed.

## Notes
- No build step, no dependencies — pure static HTML/CSS. Deploy `public/` directly.
- Fonts load from Google Fonts CDN; self-host if you want zero external requests.
- Mailchimp signup intentionally NOT here (Track R / review-wait window per roadmap).
- The word "wrong" is deliberately absent per request; the comparison uses
  "two different answers" / "off by two points" / "a bad number" instead.
