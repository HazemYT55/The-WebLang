# 📦 IOTW — Info Of The Web

**Extension:** `.iotw`
**Replaces:** JSON
**Purpose:** Stores data and connects it to MTWC logic.

**Version:** 1.1

---

## Basic Format

```
(Name : Hazem , Age : 13)
```

Simple key-value pairs, wrapped in `( )`, separated by `,`.

---

## How to Connect IOTW to MTWC

Inside the `.iotw` file:

```
link web.mtwc
(Name : [act:S] , Age : 13)
```

`[act:S]` means **"this value comes from action S in MTWC"** — so the data is dynamic, not fixed.

---

## Syntax Rules

| Symbol | Meaning | Example |
|---|---|---|
| `( ... )` | Data block | `(Name : Ali)` |
| `Key : Value` | One pair | `Age : 13` |
| `,` | Separate pairs | `(A : 1 , B : 2)` |
| `[act:X]` | Value from MTWC action | `Name : [act:S]` |
| `link web.mtwc` | Connect to logic file | `link web.mtwc` |

---

## Example 1 — Static Data

```
(Name : Hazem , Age : 13)
```

---

## Example 2 — Connected to MTWC

**`data.iotw`**
```
link web.mtwc
(Name : [act:S] , Age : 13)
```

**`web.mtwc`**
```
action(S)
  (Name) == "Hazem"
```

**Result:** `Name` gets filled from MTWC action `S`.

---

## Example 3 — Multiple Data Blocks

```
link web.mtwc

(user : (Name : Hazem , Age : 13))
(settings : (theme : dark , lang : ar))
```

---

## Example 4 — Full Page

**`data.iotw`**
```
link web.mtwc

(profile : (Name : [act:S] , Age : 13 , Role : "Dev"))
(theme : (mode : dark , color : "blue"))
```

**`web.mtwc`**
```
action(S)
  (Name) == "Hazem"
```

**`page.btw`**
```
link web.mtwc
link data.iotw

t.1 "Profile"
p "Name: {profile.Name}"
p "Age: {profile.Age}"
```

---

## Cheat Sheet

```
( ... )            → data block
Key : Value        → one pair
,                  → separate
[act:X]            → value from MTWC
link web.mtwc      → connect logic
```

---

## Common Mistakes

- Forgetting `( )` around data → `(Name : Ali)` ✅ / `Name : Ali` ❌
- Forgetting `,` between pairs → `(A:1 , B:2)` ✅
- Forgetting `link web.mtwc` when using `[act:X]`
- Using `[act:X]` without the matching action in MTWC → empty value

---

## Old Way vs New Way

**Old (JSON):**
```json
{
  "Name": "Hazem",
  "Age": 13
}
```

**New (IOTW):**
```
(Name : Hazem , Age : 13)
```
