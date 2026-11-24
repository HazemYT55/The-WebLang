# 📄 BTW — Base Text Web

**Extension:** `.btw`
**Replaces:** HTML
**Purpose:** Structure and content of a web page using simple, readable tags.

**Version:** 1.1

---

## Basic Format

```
title : My Page

t.1 "Welcome to my page"
btn "Click me"
img: photo.jpg
```

---

## 🆕 What's New in v1.1

| Feature | What it does |
|---|---|
| **Media attributes** | `vid: URL [autoplay] [mute] [loop]` |
| **Custom components** | Define once, reuse anywhere with `use` |
| **Component slots** | Pass content into components |
| **Multi-page links** | `a "Next" -> page2.btw` (internal pages) |

---

## All Tags

### 📄 Page Tags

| Tag | What it's for | Example |
|---|---|---|
| `title` | Puts the title of the page | `title : My Page` |
| `link` | Connects STW / MTWC files | `link web.stw` |
| `meta` | Page info (author, keywords) | `meta author : Ali` |
| `icon` | Browser tab icon | `icon: logo.png` |

### 📝 Text Tags

| Tag | What it's for | Example |
|---|---|---|
| `t.1` – `t.6` | Headings (big → small) | `t.1 "Welcome"` |
| `p` | Paragraph of text | `p "Some words here"` |
| `b` | Bold text | `b "important"` |
| `i` | Italic text | `i "note"` |
| `u` | Underlined text | `u "link-like"` |
| `s` | Strikethrough | `s "old price"` |
| `code` | Code snippet | `code "print('hi')"` |
| `quote` | Blockquote | `quote "Famous words"` |
| `mark` | Highlighted text | `mark "highlight"` |
| `small` | Small text | `small "fine print"` |

### 🔗 Link Tags

| Tag | What it's for | Example |
|---|---|---|
| `a` | Hyperlink (external or internal). The address (HTML href) can be written as `-> url`, `href="url"` or `[href:url]` | `a "Google" -> https://google.com` or `a "Google" href="https://google.com"` |
| `a` 🆕 | Link to another BTW page | `a "Next" -> page2.btw` |
| `anchor` | Jump to a section | `anchor #top` |
| `email` | Email link | `email "mail@site.com"` |
| `phone` | Phone link | `phone "123456"` |

### 🖼️ Media Tags (v1.1: with attributes) 🆕

| Tag | What it's for | Example |
|---|---|---|
| `img` | Adds an image | `img: photo.jpg` |
| `img` 🆕 | Image with attributes | `img: photo.jpg [w:300] [alt:"My photo"]` |
| `vid` | Adds a video | `vid: 1.mp4` |
| `vid` 🆕 | Video with attributes | `vid: 1.mp4 [autoplay] [mute] [loop]` |
| `mus` | Adds music | `mus: music.mp3` |
| `mus` 🆕 | Music with attributes | `mus: music.mp3 [loop] [volume:0.5]` |
| `gif` | Adds a GIF | `gif: fun.gif` |
| `svg` | Adds an SVG icon | `svg: icon.svg` |
| `iframe` | Embeds another page | `iframe: https://site.com` |

#### 🎬 Media Attributes (v1.1)

| Attribute | Applies to | What it does |
|---|---|---|
| `[autoplay]` | `vid`, `mus` | Start playing automatically |
| `[mute]` | `vid` | Start muted |
| `[loop]` | `vid`, `mus` | Repeat forever |
| `[controls]` | `vid`, `mus` | Show play/pause buttons |
| `[w:?]` | `img`, `vid` | Set width |
| `[h:?]` | `img`, `vid` | Set height |
| `[alt:"?"]` | `img` | Alt text (for accessibility) |
| `[volume:?]` | `mus` | Volume 0.0 – 1.0 |
| `[poster:"?"]` | `vid` | Thumbnail before play |
| `[preload]` | `vid`, `mus` | Load before play |

### 🔘 Button Tags

| Tag | What it's for | Example |
|---|---|---|
| `btn` | Makes a button | `btn "Click me"` |
| `btn.icon` | Button with icon | `btn.icon "★ Save"` |
| `btn.link` | Button that opens a link | `btn.link "Go" -> /page` |
| `btn.disabled` | Disabled button | `btn.disabled "Can't click"` |

### 📋 Form Tags

| Tag | What it's for | Example |
|---|---|---|
| `form` | Wraps inputs | `form [id:1] { ... }` |
| `input` | Text field | `input email` |
| `pass` | Password field | `pass password` |
| `num` | Number field | `num age` |
| `date` | Date picker | `date birthday` |
| `textarea` | Multi-line text | `textarea message` |
| `check` | Checkbox | `check "I agree"` |
| `radio` | Pick one option | `radio "Yes"` |
| `select` | Dropdown | `select { opt "A" }` |
| `opt` | Dropdown option | `opt "A"` |
| `label` | Text next to input | `label "Name"` |
| `submit` | Submit button | `submit "Send"` |
| `range` | Slider | `range 0-100` |
| `file` | File upload | `file resume.pdf` |
| `color` | Color picker | `color theme` |

### 📦 Layout Tags

| Tag | What it's for | Example |
|---|---|---|
| `box` | Generic container | `box { ... }` |
| `row` | Horizontal layout | `row { ... }` |
| `col` | Vertical layout | `col { ... }` |
| `grid` | Grid layout | `grid { ... }` |
| `card` | Card container | `card { ... }` |
| `header` | Top of page | `header { ... }` |
| `footer` | Bottom of page | `footer { ... }` |
| `nav` | Navigation menu | `nav { ... }` |
| `section` | Content section | `section { ... }` |
| `aside` | Side content | `aside { ... }` |
| `center` | Center content | `center { ... }` |
| `space` | Empty spacing | `space 20px` |
| `line` | Horizontal divider | `line` |

### 📋 List Tags

| Tag | What it's for | Example |
|---|---|---|
| `ul` | Bullet list | `ul { li "A" }` |
| `ol` | Numbered list | `ol { li "1" }` |
| `li` | List item | `li "Apple"` |
| `dl` | Description list | `dl { dt "Word" dd "Meaning" }` |
| `dt` | Term | `dt "Word"` |
| `dd` | Definition | `dd "Meaning"` |

### 📊 Table Tags

| Tag | What it's for | Example |
|---|---|---|
| `table` | Table wrapper | `table { ... }` |
| `tr` | Table row | `tr { ... }` |
| `td` | Table cell | `td "Data"` |
| `th` | Header cell | `th "Name"` |
| `thead` | Header section | `thead { ... }` |
| `tbody` | Body section | `tbody { ... }` |
| `caption` | Table title | `caption "Scores"` |

### 🧩 Custom Components (v1.1) 🆕

| Keyword | What it's for | Example |
|---|---|---|
| `define Name` | Create a reusable component | `define Card { ... }` |
| `use Name` | Use a component | `use Card` |
| `slot` | Placeholder for custom content | `slot` |
| `prop` | Pass a value into a component | `prop title "Hello"` |

#### How Components Work

```
define Card {
  box {
    t.2 prop title
    p slot
  }
}

use Card {
  prop title "Welcome"
  slot "This is the body text."
}
```

= **Define once, use anywhere.** No copy-paste.

### 🎨 Extra Tags

| Tag | What it's for | Example |
|---|---|---|
| `progress` | Progress bar | `progress 70%` |
| `loading` | Loading spinner | `loading` |
| `tooltip` | Hover hint | `tooltip "Info"` |
| `badge` | Small label | `badge "New"` |
| `avatar` | Profile picture | `avatar: user.jpg` |
| `clock` | Live clock | `clock` |
| `count` | Counter | `count: 0` |
| `theme` | Dark / light mode | `theme dark` |
| `lang` | Page language | `lang ar` |
| `comment` | Note (hidden) | `comment "todo"` |
| `id` | Give element an id | `btn "Hi" [id:1]` |
| `class` | Group elements | `btn "Hi" [class:main]` |

---

## Examples

### Example 1 — Simple Page

```
title : My First Page

t.1 "Welcome!"
p "This is my site."
btn "Click me"
```

---

### Example 2 — Image + Link

```
title : Gallery

t.1 "My Photos"
img: photo.jpg
a "Visit Google" -> https://google.com
b "Bold note"
i "Italic note"
mark "highlighted"
```

---

### Example 3 — Media with Attributes (v1.1) 🆕

```
title : Media

t.1 "Watch and Listen"

vid: intro.mp4 [autoplay] [mute] [loop] [controls] [w:600]
mus: theme.mp3 [loop] [volume:0.3]
img: cover.jpg [w:300] [alt:"Cover image"]

btn "Play"
```

**What's new:** `[autoplay]`, `[mute]`, `[loop]`, `[controls]`, `[volume]`, `[w]`, `[alt]` — no JS needed.

---

### Example 4 — Form

```
title : Contact

t.1 "Contact Us"
form [id:1] {
  label "Name"
  input name [id:1]
  label "Email"
  input email [id:2]
  label "Password"
  pass password [id:3]
  label "Message"
  textarea message [id:4]
  check "Subscribe"
  submit "Send"
}
```

---

### Example 5 — List + Table

```
title : Data

t.1 "Fruits"
ul {
  li "Apple"
  li "Banana"
  li "Cherry"
}

t.2 "Scores"
table {
  thead {
    tr {
      th "Name"
      th "Score"
    }
  }
  tbody {
    tr {
      td "Ali"
      td "95"
    }
    tr {
      td "Sara"
      td "88"
    }
  }
}
```

---

### Example 6 — Layout Page

```
title : Layout

header {
  nav {
    a "Home" -> /
    a "About" -> /about
    a "Contact" -> page3.btw
  }
}

section {
  t.1 "About Us"
  p "We build things."
  row {
    card {
      t.2 "Fast"
      p "Very fast."
    }
    card {
      t.2 "Simple"
      p "Very simple."
    }
  }
}

footer {
  p "© 2026 My Site"
}
```

---

### Example 7 — Custom Component (v1.1) 🆕

**Define once:**

```
define ProfileCard {
  card {
    avatar: prop photo
    t.2 prop name
    p prop bio
    btn prop button
  }
}
```

**Use many times:**

```
title : Team

t.1 "Our Team"

use ProfileCard {
  prop photo "ali.jpg"
  prop name "Ali"
  prop bio "Developer"
  prop button "Contact Ali"
}

use ProfileCard {
  prop photo "sara.jpg"
  prop name "Sara"
  prop bio "Designer"
  prop button "Contact Sara"
}

use ProfileCard {
  prop photo "omar.jpg"
  prop name "Omar"
  prop bio "Manager"
  prop button "Contact Omar"
}
```

**Result:** Same card design, 3 different people — **no copy-paste**.

---

### Example 8 — Component with Slot (v1.1) 🆕

**Define with a slot:**

```
define Alert {
  box {
    t.3 prop title
    slot
  }
}
```

**Fill the slot:**

```
use Alert {
  prop title "Warning!"
  slot "Please check your input."
}

use Alert {
  prop title "Success!"
  slot "Your form was sent."
}
```

**Result:** Same alert box, different content inside.

---

### Example 9 — Full Page with Everything

```
link web.stw
link web.mtwc

title : My Portfolio

define Card {
  card {
    img: prop image [w:200] [alt:prop title]
    t.2 prop title
    p prop text
    btn prop action
  }
}

header {
  nav {
    a "Home" -> page1.btw
    a "Projects" -> page2.btw
    a "Contact" -> page3.btw
  }
}

section {
  t.1 "My Projects"
  row {
    use Card {
      prop image "app1.jpg"
      prop title "App One"
      prop text "A cool app."
      prop action "View"
    }
    use Card {
      prop image "app2.jpg"
      prop title "App Two"
      prop text "Another app."
      prop action "View"
    }
  }
}

section {
  t.1 "Watch My Demo"
  vid: demo.mp4 [controls] [w:600] [poster:"cover.jpg"]
}

footer {
  p "© 2026 My Portfolio"
}
```

---

## Cheat Sheet

```
PAGE:      title :, link, meta, icon
TEXT:      t.1–t.6, p, b, i, u, s, code, quote, mark, small
LINK:      a "text" -> url · a "text" -> page.btw · email · phone
MEDIA:     img: · vid: · mus: · gif: · svg: · iframe:
ATTRS:     [autoplay] [mute] [loop] [controls] [w:?] [h:?]
           [volume:?] [alt:"?"] [poster:"?"]
BUTTON:    btn · btn.icon · btn.link · btn.disabled
FORM:      form [id:?] · input · pass · num · date · textarea
           check · radio · select · opt · label · submit
           range · file · color
LAYOUT:    box · row · col · grid · card · header · footer
           nav · section · aside · center · space · line
LIST:      ul · ol · li · dl · dt · dd
TABLE:     table · tr · td · th · thead · tbody · caption
COMPONENT: define Name { ... } · use Name { ... }
           prop key value · slot
EXTRA:     progress · loading · tooltip · badge · avatar
           clock · count · theme · lang · comment · id · class
```

---

## Common Mistakes

- Don't forget the colon for media → `img: photo.jpg` ✅
- Don't forget quotes on text → `btn "Click me"` ✅
- Media attributes go in **square brackets** → `vid: 1.mp4 [autoplay]` ✅
- Headings go **t.1 (biggest) → t.6 (smallest)**
- `id` uses square brackets → `btn "Hi" [id:1]` ✅
- One `title` per page only
- **Components**: `define` before `use`, or it won't work
- **Components**: every `prop` inside `use` must match a `prop` in `define`

---

## Old Way vs New Way

**Old (HTML):**
```html
<html>
  <head><title>My Page</title></head>
  <body>
    <h1>Welcome to my page</h1>
    <p>Some text</p>
    <button>Click me</button>
    <img src="photo.jpg">
    <video src="intro.mp4" autoplay muted loop controls width="600"></video>
    <a href="https://google.com">Google</a>

    <!-- Copy-pasted 50 times: -->
    <div class="card">
      <img src="a.jpg"><h2>Ali</h2><p>Dev</p><button>Contact</button>
    </div>
    <div class="card">
      <img src="b.jpg"><h2>Sara</h2><p>Design</p><button>Contact</button>
    </div>
  </body>
</html>
```

**New (BTW):**
```
title : My Page

t.1 "Welcome to my page"
p "Some text"
btn "Click me"
img: photo.jpg
vid: intro.mp4 [autoplay] [mute] [loop] [controls] [w:600]
a "Google" -> https://google.com

define Card {
  card {
    img: prop photo
    t.2 prop name
    p prop bio
    btn prop button
  }
}

use Card { prop photo "a.jpg"  prop name "Ali"  prop bio "Dev"    prop button "Contact" }
use Card { prop photo "b.jpg"  prop name "Sara" prop bio "Design" prop button "Contact" }
```
