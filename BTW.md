# BTW — Base Text Web

**Extension:** `.btw`
**Replaces:** HTML
**Purpose:** Structure and content of a web page using simple, readable tags.

---

## Basic Format

```
title : My Page

t.1 "Welcome to my page"
btn "Click me"
img: photo.jpg
```

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
| `a` | Hyperlink | `a "Google" -> https://google.com` |
| `anchor` | Jump to a section | `anchor #top` |
| `email` | Email link | `email "mail@site.com"` |
| `phone` | Phone link | `phone "123456"` |

### 🖼️ Media Tags

| Tag | What it's for | Example |
|---|---|---|
| `img` | Adds an image | `img: photo.jpg` |
| `vid` | Adds a video | `vid: 1.mp4` |
| `mus` | Adds music | `mus: music.mp3` |
| `gif` | Adds a GIF | `gif: fun.gif` |
| `svg` | Adds an SVG icon | `svg: icon.svg` |
| `iframe` | Embeds another page | `iframe: https://site.com` |

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
| `form` | Wraps inputs | `form { ... }` |
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

## Example 1 — Simple Page

```
title : My First Page

t.1 "Welcome!"
p "This is my site."
btn "Click me"
```

---

## Example 2 — Page with Image + Link

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

## Example 3 — Media Page

```
title : Media

t.1 "Watch and Listen"
vid: 1.mp4
mus: music.mp3
gif: fun.gif
btn "Play"
```

---

## Example 4 — Form

```
title : Contact

t.1 "Contact Us"
form {
  label "Name"
  input text
  label "Email"
  input email
  label "Password"
  pass password
  label "Message"
  textarea message
  check "Subscribe"
  submit "Send"
}
```

---

## Example 5 — List + Table

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

## Example 6 — Layout Page

```
title : Layout

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

## Cheat Sheet

```
PAGE:      title :, link, meta, icon
TEXT:      t.1–t.6, p, b, i, u, s, code, quote, mark, small
LINK:      a "text" -> url, email, phone, anchor
MEDIA:     img:, vid:, mus:, gif:, svg:, iframe:
BUTTON:    btn, btn.icon, btn.link, btn.disabled
FORM:      form, input, pass, num, date, textarea,
           check, radio, select, opt, label, submit,
           range, file, color
LAYOUT:    box, row, col, grid, card, header, footer,
           nav, section, aside, center, space, line
LIST:      ul, ol, li, dl, dt, dd
TABLE:     table, tr, td, th, thead, tbody, caption
EXTRA:     progress, loading, tooltip, badge, avatar,
           clock, count, theme, lang, comment, id, class
```

---

## Common Mistakes

- Don't forget the colon for media → `img: photo.jpg` ✅
- Don't forget quotes on text → `btn "Click me"` ✅
- Headings go **t.1 (biggest) → t.6 (smallest)**
- `id` uses square brackets → `btn "Hi" [id:1]` ✅
- One `title` per page only

---

## Old Way vs New Way

**Old:**
```html
<html>
  <head><title>My Page</title></head>
  <body>
    <h1>Welcome to my page</h1>
    <p>Some text</p>
    <button>Click me</button>
    <img src="photo.jpg">
    <a href="https://google.com">Google</a>
  </body>
</html>
```

**New:**
```
title : My Page

t.1 "Welcome to my page"
p "Some text"
btn "Click me"
img: photo.jpg
a "Google" -> https://google.com
```
