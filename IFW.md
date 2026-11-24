# 🖼️ IFW — Image For Web

**Extension:** `.ifw`
**Replaces:** SVG
**Purpose:** Draw vector graphics (shapes, icons, logos) with simple tags.

**Version:** 1.1

---

## Basic Format

```
circle: r=50 c=red
line: from(0,0) to(100,100)
```

Shapes are **tags** with `:` then attributes.

---

## Syntax Rules

| Symbol | Meaning | Example |
|---|---|---|
| `shape:` | Draw a shape | `circle:` |
| `key=value` | Attribute | `r=50` |
| `,` | Separate attributes | `r=50 , c=red` |
| `from(x,y) to(x,y)` | Start/end points | `from(0,0) to(100,100)` |
| `c=name` | Color | `c=red` |

---

## All Shapes

| Tag | What it draws | Example |
|---|---|---|
| `circle` | Circle | `circle: r=50 c=red` |
| `square` | Square | `square: s=100 c=blue` |
| `rect` | Rectangle | `rect: w=200 h=100 c=green` |
| `line` | Line | `line: from(0,0) to(100,100) c=black` |
| `triangle` | Triangle | `triangle: s=80 c=yellow` |
| `star` | Star | `star: s=50 c=gold` |
| `polygon` | Custom shape | `polygon: points(0,0 50,0 25,50) c=red` |
| `text` | Text label | `text: "Hi" x=10 y=20 c=black` |
| `path` | Free path | `path: M0,0 L50,50 c=blue` |

---

## Example 1 — Red Circle

```
circle: r=50 c=red
```

---

## Example 2 — Logo (circle + text)

```
circle: r=40 c=blue
text: "W" x=35 y=50 c=white
```

---

## Example 3 — Simple Chart

```
rect: w=60 h=100 c=blue
rect: w=60 h=60 c=red
rect: w=60 h=30 c=green
```

---

## Example 4 — Connect IFW to BTW

**`logo.ifw`**
```
circle: r=40 c=blue
text: "W" x=35 y=50 c=white
```

**`page.btw`**
```
link logo.ifw

t.1 "My Logo"
img: logo.ifw
```

---

## Cheat Sheet

```
circle: r=? c=?          → circle
square: s=? c=?          → square
rect: w=? h=? c=?        → rectangle
line: from(x,y) to(x,y)  → line
triangle: s=? c=?        → triangle
star: s=? c=?            → star
polygon: points(...)     → custom
text: "?" x=? y=? c=?    → text
```

---

## Common Mistakes

- Forgetting `:` after shape → `circle: r=50` ✅
- Forgetting `=` in attributes → `r=50` ✅ / `r 50` ❌
- Forgetting `c=` for color → `c=red` ✅

---

## Old Way vs New Way

**Old (SVG):**
```svg
<svg width="100" height="100">
  <circle cx="50" cy="50" r="40" fill="blue"/>
  <text x="35" y="50" fill="white">W</text>
</svg>
```

**New (IFW):**
```
circle: r=40 c=blue
text: "W" x=35 y=50 c=white
```
