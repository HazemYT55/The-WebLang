# 🎨 STW — Style The Web

**Extension:** `.stw`
**Replaces:** CSS
**Purpose:** Styles BTW elements using short, fixed property tags.

**Version:** 1.1

---

## Basic Format

```
body([t.a:center],[f.f:Times],[c:white])
```

= center text + Times font + white color.

---

## How to Connect STW to BTW

In your `.btw` file:

```
link web.stw
```

---

## 🆕 What's New in v1.1

| Change | Why |
|---|---|
| **One official shortcode per property** | No more 1.1 / 1.12 / 1.13 confusion |
| **No clashes** | Every property has a unique tag |
| **IDE autocomplete ready** | Type `[` → list appears |
| **Alias system** | Old tags still work (backward compatible) |

---

## The Rule (v1.1 — Fixed)

**Every CSS property = ONE official shortcode. No levels. No clashes.**

```
color              → c
font-size          → f.si
font-style         → f.st
background-color   → bg
border-color       → bd
```

The old 1.1 / 1.12 / 1.13 levels still **work** as aliases, but the **official** tag is always the same.

---

## Full CSS → STW Table (Official v1.1)

### 🎨 Color

| CSS Property | STW | What it does | Example |
|---|---|---|---|
| `color` | `c` | Text color | `[c:white]` |
| `background-color` | `bg` | Background color | `[bg:black]` |
| `background-image` | `bg.i` | Background image | `[bg.i:bg.jpg]` |
| `border-color` | `bd` | Border color | `[bd:red]` |
| `outline-color` | `ol` | Outline color | `[ol:blue]` |
| `opacity` | `o` | Transparency | `[o:0.5]` |

### ✍️ Font & Text

| CSS Property | STW | What it does | Example |
|---|---|---|---|
| `font-family` | `f.f` | Font type | `[f.f:Times]` |
| `font-size` | `f.si` | Text size | `[f.si:20px]` |
| `font-style` | `f.st` | Italic / normal | `[f.st:italic]` |
| `font-weight` | `f.w` | Bold / normal | `[f.w:bold]` |
| `text-align` | `t.a` | Align text | `[t.a:center]` |
| `text-decoration` | `t.d` | Underline etc. | `[t.d:underline]` |
| `text-transform` | `t.t` | UPPER / lower | `[t.t:uppercase]` |
| `line-height` | `l.h` | Line spacing | `[l.h:1.5]` |
| `letter-spacing` | `l.s` | Letter spacing | `[l.s:2px]` |
| `word-spacing` | `w.s` | Word spacing | `[w.s:5px]` |

### 📦 Spacing

| CSS Property | STW | What it does | Example |
|---|---|---|---|
| `margin` | `m` | Outer space | `[m:10px]` |
| `margin-top` | `m.t` | Top outer | `[m.t:20px]` |
| `margin-bottom` | `m.b` | Bottom outer | `[m.b:20px]` |
| `margin-left` | `m.l` | Left outer | `[m.l:10px]` |
| `margin-right` | `m.r` | Right outer | `[m.r:10px]` |
| `padding` | `p` | Inner space | `[p:15px]` |
| `padding-top` | `p.t` | Top inner | `[p.t:10px]` |
| `padding-bottom` | `p.b` | Bottom inner | `[p.b:10px]` |
| `padding-left` | `p.l` | Left inner | `[p.l:10px]` |
| `padding-right` | `p.r` | Right inner | `[p.r:10px]` |
| `gap` | `g` | Flex/grid gap | `[g:10px]` |

### 📐 Size

| CSS Property | STW | What it does | Example |
|---|---|---|---|
| `width` | `w` | Width | `[w:100px]` |
| `height` | `h` | Height | `[h:50px]` |
| `min-width` | `mw` | Minimum width | `[mw:200px]` |
| `max-width` | `xw` | Maximum width | `[xw:800px]` |
| `min-height` | `mh` | Minimum height | `[mh:100px]` |
| `max-height` | `xh` | Maximum height | `[xh:500px]` |

### 🔲 Border

| CSS Property | STW | What it does | Example |
|---|---|---|---|
| `border` | `b` | Full border | `[b:1px solid red]` |
| `border-width` | `b.w` | Border thickness | `[b.w:2px]` |
| `border-style` | `b.st` | Solid / dashed | `[b.st:dashed]` |
| `border-radius` | `b.r` | Rounded corners | `[b.r:8px]` |
| `box-shadow` | `sh` | Shadow | `[sh:2px 2px gray]` |

### 📊 Layout

| CSS Property | STW | What it does | Example |
|---|---|---|---|
| `display` | `d` | Display type | `[d:flex]` |
| `position` | `pos` | Positioning | `[pos:absolute]` |
| `top` | `t` | Top offset | `[t:10px]` |
| `bottom` | `bo` | Bottom offset | `[bo:10px]` |
| `left` | `le` | Left offset | `[le:10px]` |
| `right` | `ri` | Right offset | `[ri:10px]` |
| `z-index` | `z` | Layer order | `[z:10]` |
| `flex-direction` | `fl.d` | Flex direction | `[fl.d:row]` |
| `justify-content` | `j.c` | Horizontal align | `[j.c:center]` |
| `align-items` | `a.i` | Vertical align | `[a.i:center]` |
| `overflow` | `ov` | Overflow scroll | `[ov:hidden]` |

### ✨ Effect & Motion

| CSS Property | STW | What it does | Example |
|---|---|---|---|
| `transition` | `tr` | Smooth change | `[tr:0.3s]` |
| `transform` | `tf` | Rotate / scale | `[tf:rotate(45deg)]` |
| `cursor` | `cu` | Mouse cursor | `[cu:pointer]` |
| `visibility` | `v` | Hidden but takes space | `[v:hidden]` |

---

## 🗑️ Old Levels (Still Work as Aliases)

These still work for backward compatibility, but **use the official ones above**:

| Old (1.1 / 1.12 / 1.13) | Official v1.1 |
|---|---|
| `f.s` / `f.si` / `f.siz` | `f.si` |
| `f.s` / `f.st` / `f.sty` | `f.st` |
| `b.c` / `b.co` / `b.col` | `bg` (background) or `bd` (border) |
| `p` (position clash) | `pos` |

---

## 🛠️ Clash Fixes (Solved in v1.1)

| Old Clash | v1.1 Fix |
|---|---|
| `f.si` vs `f.st` | Both unique now ✅ |
| `background-color` vs `border-color` | `bg` vs `bd` ✅ |
| `padding` vs `position` | `p` vs `pos` ✅ |
| `min-width` vs `margin` | `mw` vs `m` ✅ |

**No more guessing. Every tag is fixed forever.**

---

## Examples

### Example 1 — Center the Page

```
body([t.a:center])
```

---

### Example 2 — Font + Color

```
body([f.f:Times],[c:white])
```

---

### Example 3 — Full Body Style

```
body([t.a:center],[f.f:Times],[c:white],[bg:black])
```

---

### Example 4 — Styled Button

```
btn([bg:blue],[c:white],[p:10px],[b.r:5px],[cu:pointer])
```

= blue background, white text, padding 10px, rounded 5px, pointer cursor

---

### Example 5 — Card Component

```
card([bg:#f0f0f0],[p:20px],[b.r:8px],[sh:0 2px 5px gray])
```

= light gray card, padding 20px, rounded 8px, soft shadow

---

### Example 6 — Full Page

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
body([t.a:center],[f.f:Times],[c:white],[bg:black])
btn([bg:blue],[c:white],[p:10px],[b.r:5px])
img([w:200px],[b.r:10px],[sh:0 4px 8px gray])
```

---

### Example 7 — Dark Theme

```
body([bg:#111],[c:#eee],[f.f:Helvetica])
t.1([c:#fff],[f.si:32px])
btn([bg:#222],[c:#fff],[b:1px solid #444],[b.r:6px])
```

---

### Example 8 — Flex Layout

```
row([d:flex],[j.c:center],[a.i:center],[g:20px])
col([d:flex],[fl.d:column],[g:10px])
```

---

## Cheat Sheet

```
SYNTAX:     [prop:value]
MULTIPLE:   [a:v],[b:v],[c:v]
CONNECT:    link web.stw   (in .btw file)

COLOR:      c (text) · bg (background) · bd (border) · o (opacity)
FONT:       f.f (family) · f.si (size) · f.st (style) · f.w (weight)
TEXT:       t.a (align) · t.d (decoration) · t.t (transform)
SPACING:    m (margin) · m.t/b/l/r · p (padding) · p.t/b/l/r · g (gap)
SIZE:       w (width) · h (height) · mw · xw · mh · xh
BORDER:     b · b.w · b.st · b.r · sh (shadow)
LAYOUT:     d (display) · pos (position) · z (z-index)
            fl.d (flex-dir) · j.c (justify) · a.i (align-items)
EFFECT:     tr (transition) · tf (transform) · cu (cursor)
```

---

## Common Mistakes

- Missing brackets → `[c:white]` ✅ / `c:white` ❌
- Missing colon → `[c:white]` ✅ / `[c white]` ❌
- No commas between properties → `[c:white],[f.si:20px]` ✅
- Forgetting `link web.stw` in the `.btw` file
- Using old 1.1 levels when the official tag exists → use `f.si` not `f.s`
- Forgetting units → `[f.si:20px]` ✅ / `[f.si:20]` ❌

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

button {
  background-color: blue;
  color: white;
  padding: 10px;
  border-radius: 5px;
  cursor: pointer;
}
```

**New (STW):**
```
body([t.a:center],[f.f:Times],[c:white],[bg:black])
btn([bg:blue],[c:white],[p:10px],[b.r:5px],[cu:pointer])
```

---

## IDE Autocomplete Support (v1.1) 🆕

Your IDE should show this when you type `[`:

```
[  →  c: color
       bg: background-color
       bd: border-color
       f.f: font-family
       f.si: font-size
       f.st: font-style
       f.w: font-weight
       t.a: text-align
       p: padding
       m: margin
       b.r: border-radius
       ...
```

**Type `[f.` →** shows only font tags. **Type `[b` →** shows `bg`, `bd`, `b`, `b.r`, etc.

This kills the "I can't remember the shortcode" problem. ✅
