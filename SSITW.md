# 📽️ SSITW — Show Slides In The Web

**Extension:** `.ssitw`
**Replaces:** PPTX
**Purpose:** Build slide presentations in the browser.

**Version:** 1.1

---

## Basic Format

```
slide 1 {
  title "Welcome"
  text "My presentation"
}

slide 2 {
  title "About"
  img: photo.jpg
}
```

---

## Custom Slide Styles (in STW)

You can style each slide from STW using its **slide id**:

```
slide id = 1 ([bc:red])
```

- `[bc:red]` = **b**ackground **c**olor red (System 1.1 STW)
- Works the same as `slide([bg:red])`

---

## Syntax Rules

| Keyword | Meaning | Example |
|---|---|---|
| `slide N { }` | A slide | `slide 1 { ... }` |
| `title "?"` | Slide title | `title "Welcome"` |
| `text "?"` | Slide text | `text "Hello"` |
| `img: ?` | Slide image | `img: photo.jpg` |
| `vid: ?` | Slide video | `vid: clip.mp4` |
| `bullet { }` | Bullet list | `bullet { li "A" }` |
| `slide id = N ([...])` | Style slide N | `slide id = 1 ([bc:red])` |

---

## Example 1 — Simple Deck

```
slide 1 {
  title "Welcome"
  text "My first deck"
}

slide 2 {
  title "About Me"
  text "I'm Hazem, 13 years old"
}
```

---

## Example 2 — With Image

```
slide 1 {
  title "My Project"
  img: cover.jpg
  text "Built with WebLang"
}
```

---

## Example 3 — With Video

```
slide 1 {
  title "Demo"
  vid: demo.mp4 [autoplay] [mute]
}

slide 2 {
  title "Thanks"
  text "Questions?"
}
```

---

## Example 4 — Custom Style per Slide (STW)

**`deck.ssitw`**
```
slide 1 {
  title "Welcome"
  text "Red background"
}

slide 2 {
  title "About"
  text "Blue background"
}
```

**`deck.stw`**
```
slide id = 1 ([bc:red],[c:white])
slide id = 2 ([bc:blue],[c:white])
```

**Result:** Slide 1 = red with white text. Slide 2 = blue with white text.

---

## Example 5 — Full Deck

**`talk.ssitw`**
```
slide 1 {
  title "WebLang"
  text "The future of the web"
}

slide 2 {
  title "Why?"
  bullet {
    li "No HTML"
    li "No CSS"
    li "No JS"
  }
}

slide 3 {
  title "Demo"
  vid: demo.mp4 [controls]
}

slide 4 {
  title "Thank you!"
  text "Questions?"
}
```

**`talk.stw`**
```
slide id = 1 ([bc:black],[c:white],[t.a:center])
slide id = 2 ([bc:#222],[c:#eee])
slide id = 3 ([bc:navy],[c:white])
slide id = 4 ([bc:darkgreen],[c:white],[t.a:center])
```

---

## Cheat Sheet

```
slide N { }           → slide number N
title "?"             → slide title
text "?"              → slide text
img: ?                → slide image
vid: ?                → slide video
bullet { li "?" }     → bullet list

STYLE (from .stw):
slide id = N ([bc:red])       → background color
slide id = N ([c:white])      → text color
slide id = N ([t.a:center])   → center text
```

---

## Common Mistakes

- Forgetting `{ }` around slide content → `slide 1 { ... }` ✅
- Forgetting the number → `slide { }` ❌
- Using `[bc:red]` inside SSITW → put it in `.stw` with `slide id = N`
- Missing `slide id = N` in STW → slide gets no custom style

---

## Old Way vs New Way

**Old (PPTX):**
- Open PowerPoint
- Click Insert → New Slide
- Type title, text
- Save as .pptx

**New (SSITW):**
```
slide 1 {
  title "Welcome"
  text "My presentation"
}
```
No app needed. Just a text file. 🚀
