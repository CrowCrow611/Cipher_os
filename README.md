The password is: 1234

u can change the username and password in the settings...
the password for hack mode is shadow

to go to hack mode just type: "sudo hack shadow", in the terminal






# CIPHER_OS

> A fully-featured browser-based operating system simulation — built as a single HTML file.

CIPHER_OS is a self-contained, zero-dependency desktop environment that runs entirely in your browser. It features a windowed UI, a custom scripting language, a suite of built-in apps, and a dual-mode aesthetic system that lets you flip between a clean dark workspace and a full hacker terminal vibe.

---

## Features

### Desktop Environment
- **Lock screen** with password authentication and animated unlock
- **Draggable desktop icons** with rubber-band multi-selection
- **Windowed app system** — windows are draggable, resizable, minimizable, maximizable, and snappable to screen edges
- **Taskbar** with start menu, active window list, live clock, and mode toggle
- **Window previews** on taskbar hover

### Dual Modes
| Normal Mode | Hack Mode |
|---|---|
| Dark blue/purple palette | Full green-on-black terminal aesthetic |
| Standard UI fonts | Monospace phosphor-glow fonts |
| Subtle gradients | CRT scanlines + film grain noise |
| Standard accent colors | Neon glow effects on all UI elements |

Toggle between modes from the taskbar or via the Terminal using privilege escalation.

### Customization
- **12 wallpapers** — Default, Grid, Pure Dark, Stars, Aurora, Sunset, Ocean, Matrix, Neon City, Vaporwave, Carbon, Copper
- **10 accent colors** — Blue, Purple, Mint, Amber, Red, Orange, Hack Green, Cyan, Pink, White
- **Display controls** — brightness, window opacity, taskbar height, scanlines, noise, glow
- **Terminal fonts** — Fira Code, Share Tech Mono, VT323, Courier New
- **Settings export/import** as JSON, with factory reset

---

## Built-in Apps

| App | Description |
|---|---|
| 🖥️ **Terminal** | Fully functional shell with CipherScript interpreter and OS integration |
| ✏️ **CipherScript IDE** | Code editor with line numbers, syntax highlighting, run/save/load/export, and live preview |
| 🖼️ **Image Viewer** | Zoom, pan, filters (grayscale, invert, hue-shift), filmstrip navigation, local file loading |
| 🧱 **Tetris** | Playable Tetris with hold piece, ghost piece, progressive levels, and high score persistence |
| ✅ **To-Do** | Task manager with priorities, categories, and filters — persisted via localStorage |
| ⚙️ **Settings** | Full system configuration panel covering display, appearance, mode, sound, security, and system info |
| 🔐 **Vault** | Zero-knowledge password manager |

---

## CipherScript

CIPHER_OS ships with its own scripting language: **CipherScript**. Write and run scripts directly in the IDE or Terminal.

### Syntax Overview

```
// Variables
set x :: 42
set name :: "ghost_agent"
set data :: { version: 1.0, active: true }

// Output
emit "Hello, cipher"
signal("Alert", "Message body")

// Functions
proc add :: a, b ->
  yield a + b
::

// Conditionals
check x > 0 ->
  emit "positive"
| x is 0 ->
  emit "zero"
| ->
  emit "negative"
::

// Loops
loop i :: 0 to 9 ->
  emit str(i)
::

scan myList as item ->
  emit item
::

until x > 100 ->
  set x :: x + 1
::
```

### Operators
| Operator | Meaning |
|---|---|
| `is` | Equality (`==`) |
| `isnt` | Not equal (`!=`) |
| `not` | Logical NOT |
| `and` / `or` | Logical AND / OR |
| `++` | String concatenation |

### Built-in Functions

```
// Type conversion
str  int  float  bool

// String
len  upper  lower  trim  split  join  contains

// Math
sqrt  floor  ceil  abs  pow  max  min  rng  rand

// Array
range  push  pop  sort  reverse  keys  values

// OS / IO
emit  signal  launch  ask  time

// Utilities
json  stringify  clear  log  warn  err
```

### OS Integration
CipherScript can interact with the OS directly:

```
// Launch an app
launch("terminal")

// Send a notification
signal("CipherScript", "Hello from a script!")

// Get current timestamp
emit str(time())
```

### Example Scripts

**Fibonacci**
```
proc fib :: n ->
  check n <= 1 ->
    yield n
  ::
  yield fib(n-1) + fib(n-2)
::

loop i :: 0 to 10 ->
  emit str(fib(i))
::
```

**FizzBuzz**
```
loop i :: 1 to 20 ->
  check i % 15 is 0 ->
    emit "FizzBuzz"
  | i % 3 is 0 ->
    emit "Fizz"
  | i % 5 is 0 ->
    emit "Buzz"
  | ->
    emit str(i)
  ::
::
```

---

## Getting Started

CIPHER_OS requires no build step, no server, and no dependencies.

1. **Download** `cipher_os.html`
2. **Open** it in any modern browser (Chrome, Firefox, Edge, Safari)
3. **Log in** — default password is `cipher` (changeable in Settings → Security)

That's it. Everything runs client-side.

---

## Keyboard Shortcuts

| Shortcut | Action |
|---|---|
| `Ctrl + Enter` | Run CipherScript |
| `Ctrl + S` | Save script |
| `Tab` | Insert 2-space indent in editor |
| `←` `→` `↑` `↓` | Tetris movement / rotation |
| `Space` | Tetris hard drop |
| `C` / `Shift` | Tetris hold piece |

---

## Storage & Persistence

CIPHER_OS uses `localStorage` to persist state between sessions:

- Settings (accent color, wallpaper, display options)
- To-Do tasks
- CipherScript editor contents
- Tetris high score
- Desktop icon positions
- Login password (changeable in Settings)

Settings can be exported as a `.json` file and re-imported at any time.

---

## Browser Compatibility

Works in any modern browser that supports:
- CSS custom properties
- `localStorage`
- Canvas API
- `backdrop-filter`

> No Node.js. No npm. No framework. Just one `.html` file.

---

## License

MIT — do whatever you want with it.

---

*Built by ghost_agent using CipherScript.*


