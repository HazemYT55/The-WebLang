<p align="center">
  <img src="1-weblang-logo.png" alt="WebLang logo" width="220">
</p>

# 🌐 WebLang — BTW · STW · MTWC

A simple, readable web language that replaces **HTML**, **CSS**, and **JavaScript** with 3 clean file types.

| File | Replaces | Purpose | Extension |
|---|---|---|---|
| **BTW** | HTML | Structure & content | `.btw` |
| **STW** | CSS | Styling | `.stw` |
| **MTWC** | JavaScript | Logic & interactivity | `.mtwc` |

---

## 🚀 Quick Start

**`page.btw`**
```
link web.stw
link web.mtwc

title : My App
t.1 "Welcome" [id:1]
btn "Dark Mode" [id:2]
img: photo.jpg
```

**`web.stw`**
```
body([t.a:center],[f.fa:Times],[c:white],[b.col:black])
```

**`web.mtwc`**
```
btn.id = 2 , connect to 'web.btw':

action(Dark)
  inclick btn:
    if (Dark) == true:
      (Dark) == false
      theme light
    else
      (Dark) == true
      theme dark
```

That's a **full interactive page** in 3 tiny files. 🎉

---

# 📄 BTW — Base Text Web

**Extension:** `.btw` · **Replaces:** HTML
**Purpose:** Structure and content of a web page.

## Basic Format

```
title : My Page

t.1 "Welcome to my page"
btn "Click me"
img: photo.jpg
```

## All Tags

### Page Tags

| Tag | What it's for | Example |
|---|---|---|
| `title` | Page title (tab name) | `title : My Page` |
| `link` | Connect STW / MTWC files | `link web.stw` |
| `meta` | Page info | `meta author : Ali` |
| `icon` | Browser tab icon | `icon: logo.png` |

### Text Tags

| Tag | What it's for | Example |
|---|---|---|
| `t.1`–`t.6` | Headings (big → small) | `t.1 "Welcome"` |
| `p` | Paragraph | `p "Some words"` |
| `b` | Bold | `b "important"` |
| `i` | Italic | `i "note"` |
| `u` | Underline | `u "text"` |
| `s` | Strikethrough | `s "old"` |
| `code` | Code snippet | `code "print('hi')"` |
| `quote` | Blockquote | `quote "words"` |
| `mark` | Highlight | `mark "highlight"` |
| `small` | Small text | `small "fine print"` |

### Link Tags

| Tag | What it's for | Example |
|---|---|---|
| `a` | Hyperlink | `a "Google" -> https://google.com` |
| `anchor` | Jump to section | `anchor #top` |
| `email` | Email link | `email "mail@site.com"` |
| `phone` | Phone link | `phone "123456"` |

### Media Tags

| Tag | What it's for | Example |
|---|---|---|
| `img` | Image | `img: photo.jpg` |
| `vid` | Video | `vid: 1.mp4` |
| `mus` | Music | `mus: music.mp3` |
| `gif` | GIF | `gif: fun.gif` |
| `svg` | SVG icon | `svg: icon.svg` |
| `iframe` | Embed page | `iframe: https://site.com` |

### Button Tags

| Tag | What it's for | Example |
|---|---|---|
| `btn` | Button | `btn "Click me"` |
| `btn.icon` | Button with icon | `btn.icon "★ Save"` |
| `btn.link` | Link button | `btn.link "Go" -> /page` |
| `btn.disabled` | Disabled button | `btn.disabled "Can't click"` |

### Form Tags

| Tag | What it's for | Example |
|---|---|---|
| `form` | Input wrapper | `form { ... }` |
| `input` | Text field | `input email` |
| `pass` | Password | `pass password` |
| `num` | Number | `num age` |
| `date` | Date picker | `date birthday` |
| `textarea` | Multi-line text | `textarea message` |
| `check` | Checkbox | `check "I agree"` |
| `radio` | Radio button | `radio "Yes"` |
| `select` | Dropdown | `select { opt "A" }` |
| `opt` | Dropdown option | `opt "A"` |
| `label` | Input label | `label "Name"` |
| `submit` | Submit button | `submit "Send"` |
| `range` | Slider | `range 0-100` |
| `file` | File upload | `file resume.pdf` |
| `color` | Color picker | `color theme` |

### Layout Tags

| Tag | What it's for | Example |
|---|---|---|
| `box` | Container | `box { ... }` |
| `row` | Horizontal layout | `row { ... }` |
| `col` | Vertical layout | `col { ... }` |
| `grid` | Grid layout | `grid { ... }` |
| `card` | Card | `card { ... }` |
| `header` | Top of page | `header { ... }` |
| `footer` | Bottom of page | `footer { ... }` |
| `nav` | Navigation | `nav { ... }` |
| `section` | Section | `section { ... }` |
| `aside` | Side content | `aside { ... }` |
| `center` | Center content | `center { ... }` |
| `space` | Spacer | `space 20px` |
| `line` | Divider | `line` |

### List Tags

| Tag | What it's for | Example |
|---|---|---|
| `ul` | Bullet list | `ul { li "A" }` |
| `ol` | Numbered list | `ol { li "1" }` |
| `li` | List item | `li "Apple"` |
| `dl` | Definition list | `dl { dt "Word" dd "Meaning" }` |
| `dt` | Term | `dt "Word"` |
| `dd` | Definition | `dd "Meaning"` |

### Table Tags

| Tag | What it's for | Example |
|---|---|---|
| `table` | Table | `table { ... }` |
| `tr` | Row | `tr { ... }` |
| `td` | Cell | `td "Data"` |
| `th` | Header cell | `th "Name"` |
| `thead` | Header section | `thead { ... }` |
| `tbody` | Body section | `tbody { ... }` |
| `caption` | Table title | `caption "Scores"` |

### Extra Tags

| Tag | What it's for | Example |
|---|---|---|
| `progress` | Progress bar | `progress 70%` |
| `loading` | Spinner | `loading` |
| `tooltip` | Hover hint | `tooltip "Info"` |
| `badge` | Small label | `badge "New"` |
| `avatar` | Profile picture | `avatar: user.jpg` |
| `clock` | Live clock | `clock` |
| `count` | Counter | `count: 0` |
| `theme` | Dark / light | `theme dark` |
| `lang` | Page language | `lang ar` |
| `comment` | Hidden note | `comment "todo"` |
| `id` | Element id | `btn "Hi" [id:1]` |
| `class` | Group elements | `btn "Hi" [class:main]` |

## BTW Example

```
title : My Page

header {
  nav {
    a "Home" -> /
    a "About" -> /about
  }
}

section {
  t.1 "About Us"
  p "We build things."
  row {
    card { t.2 "Fast"  p "Very fast." }
    card { t.2 "Simple" p "Very simple." }
  }
}

footer {
  p "© 2026 My Site"
}
```

---

# 🎨 STW — Style The Web

**Extension:** `.stw` · **Replaces:** CSS
**Purpose:** Styles BTW elements using short property tags.

## Basic Format

```
body([t.a:center],[f.fa:Times],[c:white])
```

## How to Connect

In your `.btw` file:
```
link web.stw
```

## The Rule — 3 Levels

Take letters from each word of the CSS property name.

| Level | Rule | `font-size` becomes |
|---|---|---|
| **1.1** | 1 letter per word | `f.s` |
| **1.12** | 1 letter from word 1, 2 from word 2 | `f.si` |
| **1.13** | 1 letter from word 1, 3 from word 2 | `f.siz` |

Pick the level with **no clashes**.

## CSS → STW Translation Table

| CSS Property | 1.1 | 1.12 | 1.13 | What it does |
|---|---|---|---|---|
| `color` | `c` | `c` | `c` | Text color |
| `background-color` | `b.c` | `b.co` | `b.col` | Background |
| `background-image` | `b.i` | `b.im` | `b.ima` | Bg image |
| `font-family` | `f.f` | `f.fa` | `f.fam` | Font type |
| `font-size` | `f.s` | `f.si` | `f.siz` | Text size |
| `font-style` | `f.s` ❌ | `f.st` | `f.sty` | Italic |
| `font-weight` | `f.w` | `f.we` | `f.wei` | Bold |
| `text-align` | `t.a` | `t.al` | `t.ali` | Alignment |
| `text-decoration` | `t.d` | `t.de` | `t.dec` | Underline |
| `line-height` | `l.h` | `l.he` | `l.hei` | Line space |
| `letter-spacing` | `l.s` | `l.sp` | `l.spa` | Letter space |
| `margin` | `m` | `m` | `m` | Outer space |
| `margin-top` | `m.t` | `m.to` | `m.top` | Top space |
| `margin-bottom` | `m.b` | `m.bo` | `m.bot` | Bottom space |
| `margin-left` | `m.l` | `m.le` | `m.lef` | Left space |
| `margin-right` | `m.r` | `m.ri` | `m.rig` | Right space |
| `padding` | `p` | `p` | `p` | Inner space |
| `padding-top` | `p.t` | `p.to` | `p.top` | Top inner |
| `padding-bottom` | `p.b` | `p.bo` | `p.bot` | Bottom inner |
| `border` | `b` | `b` | `b` | Border |
| `border-radius` | `b.r` | `b.ra` | `b.rad` | Rounded |
| `border-color` | `b.c` ❌ | `b.co` ❌ | `b.col` ✅ | Border color |
| `border-width` | `b.w` | `b.wi` | `b.wid` | Border size |
| `width` | `w` | `w` | `w` | Width |
| `height` | `h` | `h` | `h` | Height |
| `display` | `d` | `d` | `d` | Display type |
| `position` | `p` ❌ | `p` ❌ | `p` ❌ | Position |
| `opacity` | `o` | `o` | `o` | Transparency |
| `box-shadow` | `b.s` | `b.sh` | `b.sha` | Shadow |
| `z-index` | `z.i` | `z.in` | `z.ind` | Layer order |

✅ = works · ❌ = clash → use a higher level or rename

## Clash Fixes

- **Font group:** use 1.12 → `f.si` (size) vs `f.st` (style)
- **Color group:** use 1.13 → `b.col` for both, or rename → `bg.co` / `bd.co`
- **Padding vs Position:** both `p` → rename position to `pos`

## STW Example

```
body([t.a:center],[f.fa:Times],[c:white],[b.col:black])
btn([b.co:blue],[c:white],[p:10px],[b.ra:5px])
```

---

# ⚡ MTWC — Make The Web Click

**Extension:** `.mtwc` · **Replaces:** JavaScript
**Purpose:** Logic and interactivity for BTW pages.

## Basic Format

```
btn.id = 1 , connect to 'web.btw':

action(Dark)
  inclick btn:
    if (Dark) == true:
      (Dark) == false
    else
      (Dark) == true
```

## How to Connect

1. In `.mtwc` → `connect to 'web.btw':`
2. In `.btw` → `btn "Click me" [id:1]` and `link web.mtwc`

## All Keywords

### Connection

| Keyword | What it's for | Example |
|---|---|---|
| `.id = ?` | Give an id | `btn.id = 1` |
| `connect to 'file.btw':` | Link to page | `connect to 'web.btw':` |
| `link` | Attach MTWC | `link extra.mtwc` |

### Actions

| Keyword | What it's for | Example |
|---|---|---|
| `action(Name)` | Define action | `action(Dark)` |
| `run(Name)` | Call action | `run(Dark)` |
| `stop(Name)` | Stop action | `stop(Dark)` |
| `repeat(N):` | Repeat N times | `repeat(3):` |
| `loop:` | Loop forever | `loop:` |
| `wait(N):` | Pause N sec | `wait(2):` |
| `end` | Close block | `end` |

### Events

| Keyword | What it's for | Example |
|---|---|---|
| `inclick ?` | On click | `inclick btn:` |
| `inload ?` | On page load | `inload page:` |
| `inhover ?` | On hover | `inhover btn:` |
| `inleave ?` | On leave | `inleave btn:` |
| `intype ?` | On typing | `intype input:` |
| `insubmit ?` | On submit | `insubmit form:` |
| `inscroll ?` | On scroll | `inscroll page:` |
| `inkey ?` | On key press | `inkey Enter:` |

### Logic

| Keyword | What it's for | Example |
|---|---|---|
| `if (?) == true:` | If true | `if (Dark) == true:` |
| `if (?) == false:` | If false | `if (Dark) == false:` |
| `if (?) > ?:` | Greater than | `if (count) > 10:` |
| `if (?) < ?:` | Less than | `if (count) < 0:` |
| `if (?) == "?":` | Text match | `if (name) == "Ali":` |
| `else if:` | Another check | `else if (count) == 5:` |
| `else` | Otherwise | `else` |
| `and` | Both true | `if (a) == true and (b) == true:` |
| `or` | Either true | `if (a) == true or (b) == true:` |
| `not` | Opposite | `if not (Dark) == true:` |

### Variables

| Keyword | What it's for | Example |
|---|---|---|
| `var name = ?` | Create variable | `var count = 0` |
| `(?) == true` | Set true | `(Dark) == true` |
| `(?) == false` | Set false | `(Dark) == false` |
| `(?) == ?` | Set value | `(count) == 5` |
| `(?) == (?) + 1` | Add | `(count) == (count) + 1` |
| `(?) == (?) - 1` | Subtract | `(count) == (count) - 1` |
| `(?) == (?) * ?` | Multiply | `(price) == (price) * 2` |
| `(?) == (?) / ?` | Divide | `(total) == (total) / 2` |

### Output

| Keyword | What it's for | Example |
|---|---|---|
| `show ?` | Display value | `show (count)` |
| `alert ?` | Popup | `alert "Hello!"` |
| `log ?` | Console print | `log (count)` |
| `set ?` | Change text | `set t.1 "New title"` |
| `hide ?` | Hide element | `hide box` |
| `reveal ?` | Show element | `reveal box` |
| `color ?` | Change color | `color btn "red"` |
| `size ?` | Change size | `size img "200px"` |

### Style Control

| Keyword | What it's for | Example |
|---|---|---|
| `theme dark` | Dark mode | `theme dark` |
| `theme light` | Light mode | `theme light` |
| `class add ?` | Add class | `class add btn "active"` |
| `class remove ?` | Remove class | `class remove btn "active"` |

### Math

| Keyword | What it's for | Example |
|---|---|---|
| `+ - * / %` | Basic math | `(a) + (b)` |
| `random(?,?)` | Random number | `random(1,10)` |

### Time

| Keyword | What it's for | Example |
|---|---|---|
| `now` | Current time | `show now` |
| `today` | Current date | `show today` |
| `timer(N)` | Countdown | `timer(10)` |
| `wait(N):` | Pause | `wait(2):` |

## MTWC Examples

### Example 1 — Dark Mode Toggle

**`page.btw`**
```
link web.mtwc

title : My Page
t.1 "Welcome"
btn "Toggle Dark" [id:1]
```

**`web.mtwc`**
```
btn.id = 1 , connect to 'web.btw':

action(Dark)
  inclick btn:
    if (Dark) == true:
      (Dark) == false
      theme light
    else
      (Dark) == true
      theme dark
```

### Example 2 — Counter

**`page.btw`**
```
link web.mtwc

title : Counter
t.1 "Count: 0" [id:5]
btn "+" [id:1]
btn "−" [id:2]
```

**`web.mtwc`**
```
var count = 0
connect to 'web.btw':

btn.id = 1
action(Add)
  inclick btn:
    (count) == (count) + 1
    set t.1 "Count: (count)"

btn.id = 2
action(Sub)
  inclick btn:
    (count) == (count) - 1
    set t.1 "Count: (count)"
```

### Example 3 — Login Form

**`page.btw`**
```
link web.mtwc

title : Login
form {
  input email [id:1]
  pass password [id:2]
  btn "Login" [id:3]
}
```

**`web.mtwc`**
```
btn.id = 3 , connect to 'web.btw':

action(Login)
  inclick btn:
    if (email) == "" or (password) == "":
      alert "Fill all fields!"
    else
      alert "Welcome!"
```

---

# 🔗 How the 3 Files Work Together

```
┌─────────────────────────────────────────┐
│  page.btw                               │
│  ├── structure & content                │
│  ├── link web.stw   ────┐               │
│  └── link web.mtwc  ────┼──┐            │
└─────────────────────────┼──┼────────────┘
                          │  │
              ┌───────────┘  └────────────┐
              ▼                           ▼
   ┌──────────────────┐        ┌──────────────────┐
   │  web.stw         │        │  web.mtwc        │
   │  styles          │        │  logic & events  │
   └──────────────────┘        └──────────────────┘
```

**Order matters:**
1. Write `page.btw` (structure)
2. Link `web.stw` (styles)
3. Link `web.mtwc` (logic)
4. Add `[id:N]` to any element MTWC needs to control
5. In MTWC → `connect to 'page.btw':`

---

# 📋 Full Cheat Sheet

### BTW
```
title :      → page title
t.1 – t.6    → headings
p            → paragraph
btn          → button
img: / vid: / mus:   → media
a "text" -> url      → link
[id:N]       → id for MTWC
link web.stw / web.mtwc  → connect files
```

### STW
```
SYNTAX:   [prop:value]
MULTIPLE: [a:v],[b:v]
LEVELS:   1.1 → f.s · 1.12 → f.si · 1.13 → f.siz
KEY:      c · b.col · f.fa · f.si · t.al · m.to · p · b.ra
```

### MTWC
```
CONNECT:  btn.id = 1 , connect to 'web.btw':
ACTIONS:  action / run / stop / repeat / loop / wait
EVENTS:   inclick / inload / inhover / intype / insubmit
LOGIC:    if / else if / else / and / or / not
STATE:    var x = 0 · (x) == 5 · (x) == (x) + 1
OUTPUT:   show / alert / set / hide / reveal
STYLE:    theme dark / light · class add / remove
```

---

# ✅ Common Mistakes (All Languages)

| Mistake | Fix |
|---|---|
| Media without colon | `img: photo.jpg` ✅ |
| Text without quotes | `btn "Click me"` ✅ |
| Forgot `link web.stw` | add to `.btw` file |
| Forgot `link web.mtwc` | add to `.btw` file |
| Forgot `[id:1]` in BTW | add it to the element |
| Forgot `connect to 'web.btw':` | add at top of MTWC |
| `if` without colon | `if (x) == true:` ✅ |
| `=` instead of `==` in if | `if (x) == true:` ✅ |
| Clashing STW (f.s) | use 1.12 → `f.si` |
| `padding` & `position` both `p` | rename position → `pos` |

---

# 🎯 Learn in 60 Seconds

```
1. Structure → page.btw
2. Style     → web.stw   (link it in BTW)
3. Logic     → web.mtwc  (link + connect in BTW)
4. Give ids  → [id:1] in BTW
5. Style fmt → [prop:value]
6. Logic fmt → inclick / if / (state) == value
```

**That's it. You now know WebLang.** 🎉

---

*README.md — WebLang v1.0 · BTW · STW · MTWC*
