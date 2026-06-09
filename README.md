# The IS-LM Model — Interactive Explainer

A single-page, dependency-free website that explains the IS-LM model with a live,
interactive diagram. Move the sliders for fiscal policy (G, T), monetary policy (M/P)
and the behavioural parameters (b, k, h) and the equilibrium (Y*, i*) is re-solved
in real time from the textbook equations:

```
IS:  Y  = 1/(1−c₁) · [ c₀ − c₁·T + I₀ − b·i + G ]
LM:  M/P = k·Y − h·i
```

Includes a **Japan / liquidity trap preset** (h → 60 flattens the LM curve) for the
case-study section.

## Project structure

```
index.html      ← the entire site (HTML + CSS + JS, no build step, no dependencies)
netlify.toml    ← tells Netlify there is nothing to build
README.md
```

## Deploy on Netlify (about 2 minutes)

**Option A — via Git (recommended):**

1. Create a new repository on GitHub and push these files:
   ```bash
   git init
   git add .
   git commit -m "IS-LM interactive site"
   git branch -M main
   git remote add origin https://github.com/YOUR-USERNAME/islm-site.git
   git push -u origin main
   ```
2. Log in at [app.netlify.com](https://app.netlify.com) → **Add new site → Import an existing project**.
3. Choose GitHub and select your repository.
4. Build settings: leave **Build command empty**, set **Publish directory** to `.` (the repo root) — `netlify.toml` already configures this.
5. Click **Deploy**. Done — every future `git push` redeploys automatically.

**Option B — without Git (fastest):**

Go to [app.netlify.com/drop](https://app.netlify.com/drop) and drag the project
folder into the browser window. Instant deploy, no account configuration needed.

## Customising

- All model constants live at the top of the `<script>` block in `index.html`
  (`c0`, `c1`, `I0`, the `BASE` parameters and the `PRESETS` object).
- Colours and fonts are defined as CSS variables in the `:root` block.
