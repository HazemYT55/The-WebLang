# 📝 SMDF — Show MarkDown Files

**Extension:** `.smdf`
**Replaces:** Raw `.md` files
**Purpose:** Display Markdown files as styled web content.

**Version:** 1.1

---

## Basic Format

```
show file.md
```

That's it — one line shows a whole markdown file.

---

## Syntax Rules

| Keyword | Meaning | Example |
|---|---|---|
| `show ?` | Display a markdown file | `show readme.md` |
| `link ?` | Connect STW / MTWC | `link web.stw` |
| `theme ?` | Style the markdown | `theme dark` |
| `maxw ?` | Max width | `maxw 800px` |
| `[attr]` | Options | `show file.md [toc]` |

---

## All Options

| Option | What it does | Example |
|---|---|---|
| `[toc]` | Table of contents | `show file.md [toc]` |
| `[code]` | Code highlighting | `show file.md [code]` |
| `[tables]` | Table support | `show file.md [tables]` |
| `[images]` | Show images | `show file.md [images]` |
| `[links]` | Make links clickable | `show file.md [links]` |
| `[scroll]` | Long file scrollable | `show file.md [scroll]` |
| `theme dark` | Dark mode | `theme dark` |
| `theme light` | Light mode | `theme light` |

---

## Example 1 — Simple View

```
show readme.md
```

---

## Example 2 — With Options

```
show readme.md [toc] [code] [tables] [links]
```

---

## Example 3 — Dark Theme + Width

```
theme dark
maxw 800px
show guide.md [toc] [scroll]
```

---

## Example 4 — Full Page

**`docs.smdf`**
```
link web.stw

theme dark
maxw 900px
show readme.md [toc] [code] [tables] [images] [links] [scroll]
```

**`page.btw`**
```
link web.stw
link docs.smdf

title : Docs
t.1 "Documentation"
# markdown appears here
```

---

## Cheat Sheet

```
show file.md                → show markdown
[toc]                       → table of contents
[code]                      → code highlight
[tables]                    → tables
[images]                    → images
[links]                      → clickable links
[scroll]                    → scrollable
theme dark / light          → color mode
maxw 800px                  → max width
```

---

## Common Mistakes

- Forgetting the file name → `show readme.md` ✅
- Forgetting `.md` extension → `show readme.md` ✅ / `show readme` ❌
- Using `[toc]` on a file with no headings → empty TOC

---

## Old Way vs New Way

**Old:** Open `.md` in GitHub, VSCode, or a separate markdown viewer.

**New:**
```
show readme.md [toc] [code]
```
It just **shows on the page** — no app needed. 🚀
