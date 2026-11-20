# STW — Style The Web

**Extension:** `.stw`
**Replaces:** CSS
**Purpose:** Styles BTW elements using short property tags built from CSS property names.

---

## Basic Format

```
body([a:center],[f.f:Times],[c:white])
```

---

## How to Connect STW to BTW

Inside your `.btw` file:

```
link web.stw
```

---

## The Rule — 3 Levels

Take letters from each word of the CSS property name.
**Level = how many letters you take from each word.**

| Level | Rule | `font-size` becomes |
|---|---|---|
| **1.1** | 1 letter per word | `f.s` |
| **1.12** | 1 letter from word 1, 2 letters from word 2 | `f.si` |
| **1.13** | 1 letter from word 1, 3 letters from word 2 | `f.siz` |

**Pick the level that has no clashes** — start with 1.1, go up if two properties collide.

---

## CSS → STW Translation Table (All Levels)

| CSS Property | 1.1 | 1.12 | 1.13 | What it does |
|---|---|---|---|---|
| `color` | `c` | `c` | `c` | Text color |
| `background-color` | `b.c` | `b.co` | `b.col` | Background color |
| `background-image` | `b.i` | `b.im` | `b.ima` | Background image |
| `font-family` | `f.f` | `f.fa` | `f.fam` | Font type |
| `font-size` | `f.s` | `f.si` | `f.siz` | Text size |
| `font-style` | `f.s` ❌ | `f.st` | `f.sty` | Italic / normal |
| `font-weight` | `f.w` | `f.we` | `f.wei` | Bold / normal |
| `text-align` | `t.a` | `t.al` | `t.ali` | Align text |
| `text-decoration` | `t.d` | `t.de` | `t.dec` | Underline etc. |
| `line-height` | `l.h` | `l.he` | `l.hei` | Space between lines |
| `letter-spacing` | `l.s` | `l.sp` | `l.spa` | Space between letters |
| `margin` | `m` | `m` | `m` | Outer space |
| `margin-top` | `m.t` | `m.to` | `m.top` | Top outer space |
| `margin-bottom` | `m.b` | `m.bo` | `m.bot` | Bottom outer space |
| `margin-left` | `m.l` | `m.le` | `m.lef` | Left outer space |
| `margin-right` | `m.r` | `m.ri` | `m.rig` | Right outer space |
| `padding` | `p` | `p` | `p` | Inner space |
| `padding-top` | `p.t` | `p.to` | `p.top` | Top inner space |
| `padding-bottom` | `p.b` | `p.bo` | `p.bot` | Bottom inner space |
| `border` | `b` | `b` | `b` | Border |
| `border-radius` | `b.r` | `b.ra` | `b.rad` | Rounded corners |
| `border-color` | `b.c` ❌ | `b.co` ❌ | `b.col` ✅ | Border color |
| `border-width` | `b.w` | `b.wi` | `b.wid` | Border thickness |
| `width` | `w` | `w` | `w` | Width |
| `height` | `h` | `h` | `h` | Height |
| `display` | `d` | `d` | `d` | Display type |
| `position` | `p` | `p` ❌ | `p` ❌ | Positioning |
| `opacity` | `o` | `o` | `o` | Transparency |
| `box-shadow` | `b.s` | `b.sh` | `b.sha` | Shadow |
| `z-index` | `z.i` | `z.in` | `z.ind` | Layer order |

> ✅ = works · ❌ = clash with another property

---

## Solving Clashes

Two big clash groups:

**1. Font group**
```
font-size  → f.s  (1.1)
font-style → f.s  (1.1)  ❌
```
→ Use **1.12**: `f.si` (size) vs `f.st` (style) ✅

**2. Color group**
```
background-color → b.co  (1.12)
border-color     → b.co  (1.12)  ❌
```
→ Use **1.13**: `b.col` ✅ or rename manually → `bg.co` / `bd.co`

**3. Padding vs Position**
```
padding  → p
position → p  ❌
```
→ At any level these clash. Pick one to rename → `p` = padding, `pos` = position.

---

## Example 1 — Center the Page (1.1)

```
body([t.a:center])
```

---

## Example 2 — Font + Color (1.1)

```
body([f.f:Times],[c:white])
```

---

## Example 3 — Mixed Levels (best of each)

```
body([t.a:center],[f.fa:Times],[c:white],[b.col:black])
```

= center + Times + white text + black background

---

## Example 4 — Styled Button

```
btn([b.co:blue],[c:white],[p:10px],[b.ra:5px])
```

= blue background, white text, padding 10px, rounded 5px

---

## Example 5 — Full Page

**`page.btw`**
```
link web.stw

title : My Page
t.1 "Welcome"
btn "Click me"
img: photo.jpg
```

**`web.stw`**
```
body([t.a:center],[f.fa:Times],[c:white],[b.col:black])
```

---

## Cheat Sheet

```
SYNTAX:     [prop:value]
MULTIPLE:   [a:v],[b:v],[c:v]
CONNECT:    link web.stw   (in .btw file)

LEVELS:
  1.1   → f.s      (1 letter per word)
  1.12  → f.si     (1 + 2 letters)
  1.13  → f.siz    (1 + 3 letters)

COMMON:
  c      → color
  b.co   → background-color
  f.fa   → font-family
  f.si   → font-size
  t.al   → text-align
  m.to   → margin-top
  p      → padding
  b.ra   → border-radius
  w      → width
  h      → height
```

---

## Common Mistakes

- Missing brackets → `[c:white]` ✅ / `c:white` ❌
- Missing colon → `[c:white]` ✅ / `[c white]` ❌
- No commas between properties → `[c:white],[f.si:20px]` ✅
- Forgetting `link web.stw` in the `.btw` file
- Using 1.1 when it clashes (e.g. `f.s` for both font-size and font-style) → switch to 1.12
- `padding` and `position` both = `p` → rename one (`pos`)

---

## Old Way vs New Way

**Old (CSS):**
```css
body {
  text-align: center;
  font-family: Times;
  color: white;
  background-color: black;
}
```

**New (STW):**
```
body([t.a:center],[f.fa:Times],[c:white],[b.col:black])
```
