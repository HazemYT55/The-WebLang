# MTWC — Make The Web Click

**Extension:** `.mtwc`
**Replaces:** JavaScript
**Purpose:** Adds logic, actions, and interactivity to a BTW page.

---

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

---

## How to Connect MTWC to BTW

Two things must match:

1. In the **`.mtwc`** file → `connect to 'web.btw':`
2. In the **`.btw`** file, the element needs an **id**:
   ```
   btn "Click me" [id:1]
   ```

Also link the file in BTW:
```
link web.mtwc
```

---

## All Keywords

### 🔌 Connection

| Keyword | What it's for | Example |
|---|---|---|
| `.id = ?` | Give an element an id | `btn.id = 1` |
| `connect to 'file.btw':` | Link logic to a BTW page | `connect to 'web.btw':` |
| `link` | Attach another MTWC file | `link extra.mtwc` |

### ⚡ Actions

| Keyword | What it's for | Example |
|---|---|---|
| `action(Name)` | Start an action / function | `action(Dark)` |
| `run(Name)` | Call an action | `run(Dark)` |
| `stop(Name)` | Stop an action | `stop(Dark)` |
| `repeat(N):` | Repeat code N times | `repeat(3):` |
| `loop:` | Loop forever | `loop:` |
| `wait(N):` | Wait N seconds | `wait(2):` |
| `end` | End a block | `end` |

### 🖱️ Events

| Keyword | What it's for | Example |
|---|---|---|
| `inclick ?` | When element is clicked | `inclick btn:` |
| `inload ?` | When page loads | `inload page:` |
| `inhover ?` | When mouse hovers | `inhover btn:` |
| `inleave ?` | When mouse leaves | `inleave btn:` |
| `intype ?` | When user types | `intype input:` |
| `insubmit ?` | When form is submitted | `insubmit form:` |
| `inscroll ?` | When user scrolls | `inscroll page:` |
| `inkey ?` | When key is pressed | `inkey Enter:` |

### 🔀 Logic

| Keyword | What it's for | Example |
|---|---|---|
| `if (?) == true:` | Condition (true) | `if (Dark) == true:` |
| `if (?) == false:` | Condition (false) | `if (Dark) == false:` |
| `if (?) > ?:` | Greater than | `if (count) > 10:` |
| `if (?) < ?:` | Less than | `if (count) < 0:` |
| `if (?) == "?":` | Compare text | `if (name) == "Ali":` |
| `else if:` | Another condition | `else if (count) == 5:` |
| `else` | Otherwise | `else` |
| `and` | Both true | `if (a) == true and (b) == true:` |
| `or` | Either true | `if (a) == true or (b) == true:` |
| `not` | Opposite | `if not (Dark) == true:` |

### 📦 Variables (State)

| Keyword | What it's for | Example |
|---|---|---|
| `var name = ?` | Create a variable | `var count = 0` |
| `(?) == true` | Set state true | `(Dark) == true` |
| `(?) == false` | Set state false | `(Dark) == false` |
| `(?) == ?` | Set value | `(count) == 5` |
| `(?) == (?) + 1` | Add 1 | `(count) == (count) + 1` |
| `(?) == (?) - 1` | Subtract 1 | `(count) == (count) - 1` |
| `(?) == (?) * ?` | Multiply | `(price) == (price) * 2` |
| `(?) == (?) / ?` | Divide | `(total) == (total) / 2` |

### 📝 Text / Output

| Keyword | What it's for | Example |
|---|---|---|
| `show ?` | Display value | `show (count)` |
| `alert ?` | Popup message | `alert "Hello!"` |
| `log ?` | Print to console | `log (count)` |
| `set ?` | Change element text | `set t.1 "New title"` |
| `hide ?` | Hide element | `hide box` |
| `reveal ?` | Show element | `reveal box` |
| `color ?` | Change color | `color btn "red"` |
| `size ?` | Change size | `size img "200px"` |

### 🎨 Style Control

| Keyword | What it's for | Example |
|---|---|---|
| `theme dark` | Switch to dark mode | `theme dark` |
| `theme light` | Switch to light mode | `theme light` |
| `class add ?` | Add a class | `class add btn "active"` |
| `class remove ?` | Remove a class | `class remove btn "active"` |

### 🔢 Math

| Keyword | What it's for | Example |
|---|---|---|
| `+` | Add | `(a) + (b)` |
| `-` | Subtract | `(a) - (b)` |
| `*` | Multiply | `(a) * (b)` |
| `/` | Divide | `(a) / (b)` |
| `%` | Remainder | `(a) % 2` |
| `random(?,?)` | Random number | `random(1,10)` |

### 🕒 Time

| Keyword | What it's for | Example |
|---|---|---|
| `now` | Current time | `show now` |
| `today` | Current date | `show today` |
| `timer(N)` | Countdown N sec | `timer(10)` |
| `wait(N):` | Pause N sec | `wait(2):` |

---

## Example 1 — Toggle (Dark Mode)

**`web.btw`**
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

---

## Example 2 — Counter with +1 / −1

**`web.btw`**
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

---

## Example 3 — Login Form

**`web.btw`**
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

## Example 4 — Timer Countdown

**`web.btw`**
```
link web.mtwc

title : Timer
t.1 "10" [id:1]
btn "Start" [id:2]
```

**`web.mtwc`**
```
var time = 10
btn.id = 2 , connect to 'web.btw':

action(Start)
  inclick btn:
    timer(10)
      (time) == (time) - 1
      set t.1 "(time)"
      if (time) == 0:
        alert "Time up!"
        stop(Start)
```

---

## Example 5 — Loop + Wait (animation)

```
action(Blink)
  loop:
    color btn "red"
    wait(1):
    color btn "blue"
    wait(1):
```

---

## Example 6 — Show / Hide

**`web.btw`**
```
link web.mtwc

title : Toggle Info
btn "Show Info" [id:1]
p "Secret info here" [id:2]
```

**`web.mtwc`**
```
var open = false
btn.id = 1 , connect to 'web.btw':

action(ToggleInfo)
  inclick btn:
    if (open) == true:
      (open) == false
      hide p
    else
      (open) == true
      reveal p
```

---

## Example 7 — Full Page (BTW + STW + MTWC)

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

---

## Cheat Sheet

```
CONNECT:   btn.id = 1 , connect to 'web.btw':
           link web.mtwc   (in .btw file)

ACTIONS:   action(Name) · run(Name) · stop(Name)
           repeat(N): · loop: · wait(N): · end

EVENTS:    inclick · inload · inhover · inleave
           intype · insubmit · inscroll · inkey

LOGIC:     if (...) == true: · if (...) == false:
           else if: · else
           and · or · not
           > · < · ==

STATE:     var x = 0
           (x) == 5 · (x) == (x) + 1

OUTPUT:    show · alert · log · set
           hide · reveal · color · size

STYLE:     theme dark · theme light
           class add · class remove

MATH:      + - * / % · random(a,b)

TIME:      now · today · timer(N) · wait(N):
```

---

## Common Mistakes

- Forgetting `connect to 'web.btw':` → logic won't attach
- Forgetting the **id** in BTW → `btn "Click me" [id:1]` ✅
- Forgetting `link web.mtwc` in the `.btw` file
- `if` must end with a **colon** → `if (Dark) == true:` ✅
- Using `=` inside `if` instead of `==` → `if (Dark) == true:` ✅
- Forget to close blocks with `end` when nesting deep
- `else` has no colon → `else` ✅ / `else:` ❌
- Variable must be declared first → `var count = 0`

---

## Old Way vs New Way

**Old (JS):**
```html
<button id="btn">Toggle Dark</button>
<h1 id="title">Count: 0</h1>
<script>
  let Dark = false;
  let count = 0;
  document.getElementById('btn').onclick = () => {
    Dark = !Dark;
    document.body.classList.toggle('dark');
  };
  setInterval(() => {
    count++;
    document.getElementById('title').textContent = 'Count: ' + count;
  }, 1000);
</script>
```

**New (MTWC):**
```
var Dark = false
var count = 0

btn.id = 1 , connect to 'web.btw':

action(Dark)
  inclick btn:
    if (Dark) == true:
      (Dark) == false
      theme light
    else
      (Dark) == true
      theme dark

action(Tick)
  loop:
    (count) == (count) + 1
    set t.1 "Count: (count)"
    wait(1):
```
