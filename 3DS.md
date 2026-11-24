# 🧊 3DS — 3D Show

**Extension:** `.3ds`
**Replaces:** 3D scene files (Three.js, OBJ)
**Purpose:** Build 3D scenes with simple tags.

**Version:** 1.1

---

## Basic Format

```
scene {
  cube: size=100 c=red
  light: top
  camera: front
}
```

---

## Syntax Rules

| Keyword | Meaning | Example |
|---|---|---|
| `scene { }` | 3D scene wrapper | `scene { ... }` |
| `cube:` | Cube | `cube: size=100 c=red` |
| `sphere:` | Sphere | `sphere: r=50 c=blue` |
| `plane:` | Flat plane | `plane: w=500 h=500 c=green` |
| `light:` | Light source | `light: top` |
| `camera:` | Camera view | `camera: front` |
| `rotate: ?` | Rotate object | `rotate: 45` |
| `move: ?` | Move object | `move: x=10 y=0 z=0` |
| `[spin]` | Auto-rotate | `cube: size=100 [spin]` |
| `[click]` | Clickable | `cube: [click]` |

---

## All Shapes

| Tag | What it draws | Example |
|---|---|---|
| `cube:` | Cube / box | `cube: size=100 c=red` |
| `sphere:` | Sphere / ball | `sphere: r=50 c=blue` |
| `plane:` | Flat ground | `plane: w=500 h=500 c:gray` |
| `cylinder:` | Cylinder | `cylinder: r=30 h=100 c=green` |
| `cone:` | Cone | `cone: r=30 h=80 c=yellow` |
| `torus:` | Donut | `torus: r=50 t=10 c=pink` |
| `model:` | Load a 3D model | `model: car.glb` |

---

## All Lights

| Light | What it does | Example |
|---|---|---|
| `top` | From above | `light: top` |
| `front` | From front | `light: front` |
| `side` | From side | `light: side` |
| `sun` | Sunlight | `light: sun` |
| `point` | Point light | `light: point x=10 y=20` |
| `none` | No light | `light: none` |

---

## All Cameras

| Camera | View | Example |
|---|---|---|
| `front` | Front view | `camera: front` |
| `top` | Top-down | `camera: top` |
| `side` | Side view | `camera: side` |
| `orbit` | Rotating view | `camera: orbit` |
| `free` | Free move | `camera: free` |

---

## Example 1 — Simple Cube

```
scene {
  cube: size=100 c=red
  light: top
  camera: front
}
```

---

## Example 2 — Rotating Cube

```
scene {
  cube: size=100 c=blue [spin]
  light: sun
  camera: orbit
}
```

---

## Example 3 — Clickable Sphere

```
scene {
  sphere: r=50 c=green [click]
  light: top
  camera: front
}
```

---

## Example 4 — 3D Model + Ground

```
scene {
  plane: w=500 h=500 c:gray
  model: car.glb
  light: sun
  camera: orbit
}
```

---

## Example 5 — Full Scene with BTW

**`model.3ds`**
```
scene {
  plane: w=1000 h=1000 c:#222
  cube: size=100 c=red [spin]
  sphere: r=60 c=blue
  light: sun
  camera: orbit
}
```

**`page.btw`**
```
link model.3ds

title : 3D Demo
t.1 "My 3D Scene"
# 3D scene appears here
```

---

## Cheat Sheet

```
scene { }               → 3D scene
cube: size=? c=?        → cube
sphere: r=? c=?         → sphere
plane: w=? h=? c=?      → flat ground
cylinder / cone / torus → more shapes
model: file.glb         → load model

light: top / front / side / sun / point
camera: front / top / side / orbit / free

[spin]                  → auto-rotate
[click]                 → clickable

rotate: ?               → rotate by degrees
move: x=? y=? z=?       → move in 3D
```

---

## Common Mistakes

- Forgetting `scene { }` → nothing shows
- Forgetting `light:` → scene is black
- Forgetting `camera:` → wrong view
- Using `[spin]` on many objects → performance drop

---

## Old Way vs New Way

**Old (Three.js):**
```javascript
const scene = new THREE.Scene();
const geo = new THREE.BoxGeometry(100,100,100);
const mat = new THREE.MeshBasicMaterial({color:0xff0000});
const cube = new THREE.Mesh(geo, mat);
scene.add(cube);
// ... 20+ more lines
```

**New (3DS):**
```
scene {
  cube: size=100 c=red
  light: top
  camera: front
}
```
