# Licensed brand fonts — drop-in location

The app already prefers the licensed brand faces in its CSS variables
(`--pm-display: "Mabry Pro", …`, `--pm-accent-face: "Montagu Slab", …`,
`--pm-body: "Switzer", …`). They fall back to near-match web fonts until the
licensed files are present. To activate the real brand type, drop the licensed
font files into THIS folder with these exact names, then redeploy:

- `MabryPro-Bold.woff2`        → display / headlines (Mabry Pro Bold)
- `MontaguSlab-Regular.woff2`  → accent labels / eyebrows (Montagu Slab Regular)
- `Switzer-Regular.woff2`      → body / data (Switzer Regular)
- `Switzer-Medium.woff2`       → optional, body emphasis
- `Switzer-Semibold.woff2`     → optional, headings within body

`.woff2` is preferred (smallest). If you only have `.otf`/`.ttf`, add matching
`@font-face` `src` entries in `src/brand/tokens.css` (the block is already
scaffolded there) or convert to woff2 first.

No code change is needed beyond placing the files — the `@font-face` rules in
`tokens.css` reference `/fonts/<name>.woff2` and the CSS variables already list
the licensed family names first.
