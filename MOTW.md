# 🖥️ MOTW — Media Of The Web

**Extension:** `.motw`
**Replaces:** PHP
**Purpose:** Server-side logic and dynamic content generation.

**Version:** 1.1

---

## Basic Format

```
link page.btw

make it (PHP) #you can use JS/MTWC
make var(1) = show_vid "https://link.com/video.mp4"
```

MOTW **creates new BTW tags** on the server, then sends them to the page.

---

## How MOTW Connects

1. In `.motw` → `link page.btw`
2. Then tell it what to do → `make it (PHP)`
3. Use `make var(N)` to create a tag

---

## Syntax Rules

| Keyword | Meaning | Example |
|---|---|---|
| `link page.btw` | Target page | `link page.btw` |
| `make it (PHP)` | Server mode (PHP / MTWC) | `make it (PHP)` |
| `make var(N)` | Create tag #N | `make var(1)` |
| `show_vid "url"` | Create a video tag | `show_vid "https://..."` |
| `# comment` | Note | `# this is a note` |

---

## Example 1 — Basic Video Tag

```
link page.btw

make it (PHP)
make var(1) = show_vid "https://example.com/video.mp4"
```

**Result:** `page.btw` gets a new `vid` tag with that URL.

---

## Example 2 — With MTWC Mode

```
link page.btw
link web.mtwc

make it (MTWC)
make var(1) = show_vid "https://example.com/video.mp4"
```

**Result:** The tag is created using MTWC logic instead of PHP.

---

## Example 3 — Multiple Tags

```
link page.btw

make it (PHP)
make var(1) = show_vid "https://example.com/a.mp4"
make var(2) = show_img "https://example.com/pic.jpg"
make var(3) = show_text "Hello from the server"
```

---

## Example 4 — Full Setup

**`server.motw`**
```
link page.btw

make it (PHP)
make var(1) = show_vid "https://example.com/intro.mp4"
make var(2) = show_text "Welcome to my site"
```

**`page.btw`**
```
title : My Page
t.1 "Welcome"
# var(1) and var(2) appear here automatically
```

---

## Cheat Sheet

```
link page.btw        → target page
make it (PHP)        → server mode (PHP)
make it (MTWC)       → server mode (JS/MTWC)
make var(N)          → create tag N
show_vid "url"       → create video tag
show_img "url"       → create image tag
show_text "text"     → create text tag
# comment            → note
```

---

## Common Mistakes

- Forgetting `link page.btw` → nothing connects
- Forgetting `make it (...)` → doesn't know which engine
- Reusing the same `var(N)` number → tags overwrite
- Missing quotes around URL → breaks

---

## Old Way vs New Way

**Old (PHP):**
```php
<?php
echo '<video src="https://example.com/video.mp4"></video>';
?>
```

**New (MOTW):**
```
link page.btw
make it (PHP)
make var(1) = show_vid "https://example.com/video.mp4"
```
