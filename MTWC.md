# ⚡ MTWC — Make The Web Cool

**Extension:** `.mtwc`
**Replaces:** JavaScript
**Purpose:** Adds logic, actions, and interactivity to a BTW page.

**Version:** 1.1

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

## 🆕 What's New in v1.1

| Feature | What it does |
|---|---|
| **`get input.id`** | Read what the user typed into a form field |
| **`get form.id`** | Read all fields in a form at once |
| **Multi-page variables** | Keep state across pages with `save` / `load` |
| **`define` + `use`** | Reusable logic blocks (like components) |

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
| `define(Name)` 🆕 | Define a reusable block | `define(Save)` |
| `use(Name)` 🆕 | Use a defined block | `use(Save)` |

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
| `inchange ?` 🆕 | When input value changes | `inchange input:` |

### 📝 Form Data Reading 🆕

| Keyword | What it's for | Example |
|---|---|---|
| `get input.id` | Read one input's value | `get input.4` |
| `get form.id` | Read all form fields | `get form.1` |
| `get input.id == "?"` | Check if input matches text | `if get input.4 == "Ali":` |
| `clear input.id` | Empty an input | `clear input.4` |
| `clear form.id` | Empty all form fields | `clear form.1` |

### 🔀 Logic

| Keyword | What it's for | Example |
|---|---|---|
| `if (?) == true:` | If true | `if (Dark) == true:` |
| `if (?) == false:` | If false | `if (Dark) == false:` |
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

### 💾 Save / Load (Multi-page) 🆕

| Keyword | What it's for | Example |
|---|---|---|
| `save name` | Save variable for next page | `save count` |
| `load name` | Load saved variable | `load count` |
| `save name to 'page2'` | Save for specific page | `save count to 'page2'` |
| `load name from 'page1'` | Load from specific page | `load count from 'page1'` |

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
| `theme dark` | Dark mode | `theme dark` |
| `theme light` | Light mode | `theme light` |
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

### 🌐 Page Navigation 🆕

| Keyword | What it's for | Example |
|---|---|---|
| `go 'page.btw'` | Navigate to another page | `go 'page2.btw'` |
| `back` | Go back one page | `back` |
| `reload` | Reload current page | `reload` |
| `open 'url'` | Open external URL | `open 'https://google.com'` |

---

## Examples

### Example 1 — Toggle (Dark Mode)

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

### Example 2 — Counter

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

### Example 3 — Login Form (v1.1: form reading)

**`page.btw`**
```
link web.mtwc

title : Login
form [id:1] {
  input email [id:4]
  pass password [id:5]
  btn "Login" [id:3]
}
t.1 "Welcome back!" [id:6]
```

**`web.mtwc`**
```
btn.id = 3 , connect to 'page.btw':

action(Login)
  inclick btn:
    if get input.4 == "" or get input.5 == "":
      alert "Fill all fields!"
    else
      set t.1 "Welcome, {get input.4}!"
      clear form.1
```

**What's new:** `get input.4` reads the email, `get form.1` reads all, `clear form.1` empties the form.

---

### Example 4 — Contact Form → Show Data

**`page.btw`**
```
link web.mtwc

title : Contact
form [id:1] {
  input name [id:1]
  input email [id:2]
  textarea message [id:3]
  btn "Send" [id:4]
}
t.1 "Message sent!" [id:5]
```

**`web.mtwc`**
```
btn.id = 4 , connect to 'page.btw':

action(Send)
  inclick btn:
    if get input.1 == "":
      alert "Please enter your name"
    else if get input.2 == "":
      alert "Please enter your email"
    else:
      set t.1 "Thanks {get input.1}! We'll reply to {get input.2}."
      clear form.1
```

---

### Example 5 — Search Filter (live typing)

**`page.btw`**
```
link web.mtwc

title : Search
input text [id:1]
t.2 "Apple" [id:2]
t.2 "Banana" [id:3]
t.2 "Cherry" [id:4]
```

**`web.mtwc`**
```
input.id = 1 , connect to 'page.btw':

action(Search)
  intype input:
    if get input.1 == "a":
      reveal t.2
      reveal t.3
      hide t.4
    else:
      reveal t.2
      reveal t.3
      reveal t.4
```

---

### Example 6 — Multi-page (v1.1: routing + save)

**`page1.btw`**
```
link web.mtwc

title : Page 1
input name [id:1]
btn "Next" [id:2]
```

**`page2.btw`**
```
link web.mtwc

title : Page 2
t.1 "Hello" [id:1]
btn "Back" [id:2]
```

**`web.mtwc`**
```
connect to 'page1.btw':

btn.id = 2
action(Next)
  inclick btn:
    save name to 'page2'
    go 'page2.btw'

connect to 'page2.btw':

inload page:
  load name from 'page1'
  set t.1 "Hello {name}!"

btn.id = 2
action(Back)
  inclick btn:
    back
```

---

### Example 7 — Custom Logic Block (v1.1: define / use)

**`page.btw`**
```
link web.mtwc

title : Cards
btn "Save 1" [id:1]
btn "Save 2" [id:2]
btn "Save 3" [id:3]
```

**`web.mtwc`**
```
define(SaveCard)
  (saved) == (saved) + 1
  alert "Saved! Total: {saved}"

var saved = 0
connect to 'page.btw':

btn.id = 1
action(S1)
  inclick btn:
    use(SaveCard)

btn.id = 2
action(S2)
  inclick btn:
    use(SaveCard)

btn.id = 3
action(S3)
  inclick btn:
    use(SaveCard)
```

---

### Example 8 — Timer Countdown

**`page.btw`**
```
link web.mtwc

title : Timer
t.1 "10" [id:1]
btn "Start" [id:2]
```

**`web.mtwc`**
```
var time = 10
btn.id = 2 , connect to 'page.btw':

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

### Example 9 — Show / Hide

**`page.btw`**
```
link web.mtwc

title : Toggle Info
btn "Show Info" [id:1]
p "Secret info here" [id:2]
```

**`web.mtwc`**
```
var open = false
btn.id = 1 , connect to 'page.btw':

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

### Example 10 — Full Page (BTW + STW + MTWC)

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
btn.id = 2 , connect to 'page.btw':

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
           define(Name) · use(Name)

EVENTS:    inclick · inload · inhover · inleave
           intype · insubmit · inscroll · inkey · inchange

FORM:      get input.id · get form.id
           clear input.id · clear form.id

LOGIC:     if (...) == true: · if (...) == false:
           else if: · else · and · or · not · > · <

STATE:     var x = 0
           (x) == 5 · (x) == (x) + 1
           save x · load x

OUTPUT:    show · alert · log · set
           hide · reveal · color · size

STYLE:     theme dark · theme light
           class add · class remove

MATH:      + - * / % · random(a,b)

TIME:      now · today · timer(N) · wait(N):

NAV:       go 'page.btw' · back · reload · open 'url'
```

---

## Common Mistakes

- Forgetting `connect to 'web.btw':` → logic won't attach
- Forgetting the **id** in BTW → `btn "Click me" [id:1]` ✅
- Forgetting `link web.mtwc` in the `.btw` file
- `if` must end with a **colon** → `if (Dark) == true:` ✅
- Using `=` inside `if` instead of `==` → `if (Dark) == true:` ✅
- Reading input before user types → `get input.4` returns `""`
- Forgetting to `save` before `go` on multi-page → variable lost
- `else` has no colon → `else` ✅ / `else:` ❌
- Variable must be declared first → `var count = 0`

---

## Old Way vs New Way

**Old (JS):**
```javascript
let Dark = false;
let count = 0;

document.getElementById('btn').onclick = () => {
  Dark = !Dark;
  document.body.classList.toggle('dark');
};

document.getElementById('form').onsubmit = (e) => {
  e.preventDefault();
  const name = document.getElementById('name').value;
  if (!name) alert('Enter name');
  else document.getElementById('msg').textContent = 'Hi ' + name;
};
```

**New (MTWC):**
```
var Dark = false
var count = 0

btn.id = 1 , connect to 'page.btw':
action(Dark)
  inclick btn:
    if (Dark) == true:
      (Dark) == false
      theme light
    else
      (Dark) == true
      theme dark

btn.id = 2
action(Send)
  inclick btn:
    if get input.1 == "":
      alert "Enter name"
    else
      set t.1 "Hi {get input.1}!"
```
