# 🍼 Truong Fridge Homepage

Custom homepage for the Samsung Bespoke fridge's 9" screen (1024×600px), themed for Mai & Binh's Baby Shower.

**Live URL:** https://binhftw.github.io/truongfridge/

---

## Quick-update cheat sheet

All edits are in one file: `index.html`

### Change the title

```html
<div class="title-line">Mai &amp; Binh's Baby Shower</div>
```
> Use `&amp;` for `&` inside HTML.

### Change the script subtitle ("a little bean is brewing!")

```html
<div class="script-label">a little bean is brewing!</div>
```

### Change the tagline

```html
<div class="tagline">Sip, Savor &amp; Shower &nbsp;—&nbsp; July 2026</div>
```

### Change the main emoji / icon

```html
<div class="icon-side">🍼</div>
```
Swap `🍼` for any emoji (e.g. `👶`, `🧸`, `🎀`).

### Change the background deco emojis

```html
<span class="deco d1">🍼</span>
<span class="deco d2">👶</span>
<!-- … d3 through d10 -->
```
Ten spots total. Just swap the emoji characters.

---

## Changing colors

All colors are CSS variables at the top of `<style>`:

```css
:root {
  --brown-dark: #3e1f0d;   /* main text */
  --brown:      #5c3317;   /* secondary text, clock */
  --brown-light:#8b5e3c;   /* muted text, script label */
  --cream:      #fdf8f0;   /* page background */
  --pink:       #f2a6b8;   /* divider, accents */
  --pink-light: #fce4ec;   /* icon box background */
  --pink-stripe:#f8c8d8;   /* awning stripes */
  --white:      #fffef9;   /* card background */
}
```

### Awning stripes
The striped awning at the top uses `--pink-stripe` and `--white`. To change stripe width, find:
```css
repeating-linear-gradient(to right, var(--pink-stripe) 0px, var(--pink-stripe) 32px, var(--white) 32px, var(--white) 64px)
```
The `32px` value controls stripe width.

---

## Fonts

Loaded from Google Fonts — no install needed:

| Font | Used for |
|---|---|
| **Playfair Display** | Main title |
| **Sacramento** | Script subtitle |
| **DM Sans** | Tagline, clock |

To swap fonts, update the Google Fonts `<link>` tag and the relevant `font-family:` rule in the CSS.

---

## Design constraints (fridge browser is slow)

- Fixed viewport: **1024×600px** — don't change `width: 1024px` / `height: 600px`
- **No** `filter: blur()` or `backdrop-filter`
- **No** JavaScript-spawned DOM elements
- **No** CSS animations (keep the page fully static)
- Clock updates every **30 seconds** (not faster)
- Keep total DOM elements under ~30

---

## Preview locally

```bash
cd truongfridge
python3 -m http.server 8080
# open http://localhost:8080 in a browser
# set browser window to 1024×600 for accurate preview
```

---

## Deploy

Changes go live automatically via GitHub Pages when pushed to `main`:

```bash
git add index.html
git commit -m "your message"
git push origin main
# live at https://binhftw.github.io/truongfridge/ within ~1 min
```
