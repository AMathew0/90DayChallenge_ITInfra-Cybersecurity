---

# ⚡ Vim Editor – Handy & Commonly Used Cheatsheet

Vim is a powerful, modal-based text editor. 

---

## 🚦 Vim Modes

| Mode      | Description                         |
| --------- | ----------------------------------- |
| `Normal`  | Navigation & command mode (default) |
| `Insert`  | Text insertion (`i`, `a`, etc.)     |
| `Visual`  | Select text (`v`, `V`, `Ctrl + v`)  |
| `Command` | Execute commands (`:`)              |

---

## ⌨️ Mode Switching

| Key        | Action                        |
| ---------- | ----------------------------- |
| `i`        | Insert before cursor          |
| `I`        | Insert at beginning of line   |
| `a`        | Append after cursor           |
| `A`        | Append at end of line         |
| `Esc`      | Return to Normal mode         |
| `v`        | Start visual mode (char-wise) |
| `V`        | Start visual mode (line-wise) |
| `Ctrl + v` | Start visual block mode       |
| `:`        | Command-line mode             |

---

## 📁 File Operations (in Command mode)

| Command       | Action              |
| ------------- | ------------------- |
| `:w`          | Save file           |
| `:q`          | Quit Vim            |
| `:q!`         | Quit without saving |
| `:wq` or `ZZ` | Save and quit       |
| `:e filename` | Open another file   |
| `:saveas new` | Save to new file    |

---

## 📄 Editing Text

| Key/Command | Action                    |
| ----------- | ------------------------- |
| `x`         | Delete character          |
| `dd`        | Delete (cut) current line |
| `yy` or `Y` | Copy current line         |
| `p`         | Paste after cursor        |
| `P`         | Paste before cursor       |
| `u`         | Undo                      |
| `Ctrl + r`  | Redo                      |
| `r<char>`   | Replace character         |
| `cw`        | Change word               |
| `C`         | Change to end of line     |

---

## 🔍 Search & Replace

| Command         | Action                      |
| --------------- | --------------------------- |
| `/word`         | Search forward for "word"   |
| `?word`         | Search backward             |
| `n`             | Repeat last search forward  |
| `N`             | Repeat last search backward |
| `:%s/old/new/g` | Replace all in file         |
| `:s/old/new/`   | Replace on current line     |

---

## 🧭 Navigation

| Key        | Action                    |
| ---------- | ------------------------- |
| `h`        | Left                      |
| `j`        | Down                      |
| `k`        | Up                        |
| `l`        | Right                     |
| `0`        | Start of line             |
| `^`        | First non-blank character |
| `$`        | End of line               |
| `gg`       | Top of file               |
| `G`        | End of file               |
| `:n`       | Go to line `n`            |
| `w`        | Next word                 |
| `b`        | Previous word             |
| `Ctrl + d` | Half-page down            |
| `Ctrl + u` | Half-page up              |

---

## 📦 Visual Mode Commands

| Action      | Key Sequence            |
| ----------- | ----------------------- |
| Select text | `v`, `V`, or `Ctrl + v` |
| Delete      | `d`                     |
| Copy        | `y`                     |
| Paste       | `p`                     |
| Indent      | `>` (after selecting)   |
| Unindent    | `<` (after selecting)   |

---

## 🔧 Miscellaneous

| Command       | Action                      |
| ------------- | --------------------------- |
| `:set nu`     | Show line numbers           |
| `:set nonu`   | Hide line numbers           |
| `:syntax on`  | Enable syntax highlighting  |
| `:syntax off` | Disable syntax highlighting |
| `:!cmd`       | Run shell command from Vim  |

---

## 📌 Tips for Beginners

* Always press `Esc` to return to Normal mode.
* Use `:help <topic>` to read built-in documentation (e.g., `:help yank`).
* Save often: `:w`
* Practice navigation with `hjkl`.

---
