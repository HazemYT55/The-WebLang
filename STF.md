# 📄 STF — Show Text Files

**Extension:** `.stf`
**Replaces:** Raw `.txt` files
**Purpose:** Display plain text files inside a web page.

**Version:** 1.1

---

## Basic Format

```
show notes.txt
```

---

## Syntax Rules

| Keyword | Meaning | Example |
|---|---|---|
| `show ?` | Display a text file | `show notes.txt` |
| `font ?` | Font family | `font mono` |
| `size ?` | Font size | `size 16px` |
| `color ?` | Text color | `color white` |
| `bg ?` | Background color | `bg black` |
| `maxw ?` | Max width | `maxw 800px` |
| `[wrap]` | Wrap long lines | `show notes.txt [wrap]` |
| `[scroll]` | Scrollable | `show notes.txt [scroll]` |
| `[linenums]` | Show line numbers | `show notes.txt [linenums]` |

---

## Example 1 — Simple View

```
show notes.txt
```

---

## Example 2 — Mono Font + Dark

```
font mono
size 16px
color white
bg black
show notes.txt [wrap] [scroll]
```

---

## Example 3 — With Line Numbers

```
show code.txt [linenums] [scroll]
```

---

## Example 4 — Full Page

**`viewer.stf`**
```
font mono
size 14px
color #eee
bg #111
maxw 900px
show logs.txt [linenums] [scroll] [wrap]
```

**`page.btw`**
```
link viewer.stf

title : Logs
t.1 "System Logs"
# text appears here
```

---

## Cheat Sheet

```
show file.txt           → show text file
[wrap]                  → wrap long lines
[scroll]                → scrollable
[linenums]              → line numbers
font mono / sans        → font type
size 16px               → font size
color white             → text color
bg black                → background
maxw 800px              → max width
```

---

## Common Mistakes

- Forgetting `.txt` → `show notes.txt` ✅
- Using `[linenums]` on very long files → can slow down
- Forgetting `[wrap]` → long lines overflow

---

## Old Way vs New Way

**Old:**
```html
<pre><code>
(your text file content pasted here)
</code></pre>
```

**New (STF):**
```
show notes.txt [wrap] [scroll]
```
