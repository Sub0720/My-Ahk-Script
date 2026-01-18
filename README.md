# Smart.ahk — Feature summary (for GitHub README)

**Version:** 1.0.0

**Short description**
A single-file AutoHotkey toolkit that provides global hotkeys, a lightweight autoclicker, extensive text-expansion / autocorrect hotstrings, quick utility hotkeys (close window, date/time insert), simple volume controls and a few small window/app-switch helpers. Designed to run as a single script with auto-elevation when required and an emergency suspend/exit.

---

## Key features (concise)

- **Global suspend toggle** — `F12` toggles Suspend (disables all hotkeys while on).
- **Exit script** — `Win + Shift + Q` (`#+q`) prompts to close the script.
- **AutoClicker** — Toggle left/right autoclick:
  - `Win + Alt + Left` (`#!Left`) — toggle left auto-clicker (uses a `SetTimer` sending `Click, left`).
  - `Win + Alt + Right` (`#!Right`) — toggle right auto-clicker (uses a `SetTimer` sending `Click, right`).
- **Close active window** — `Insert` closes the currently active window.
- **Quick app/window switch helpers**
  - `Right Ctrl` (`RControl`) — sends `Ctrl up` then `!{Tab}` (used to perform a quick app switch action).
  - `Right Alt` (`RAlt`) — toggles sending `Alt+W` (custom toggle behavior).
- **Volume controls** (convenient without focusing a media app)
  - `Alt + WheelUp` — Volume Up
  - `Alt + WheelDown` — Volume Down
  - `Alt + Middle-button` — Toggle Mute
- **Date & time hotstrings**
  - `;date` → inserts current date formatted `dd:MM:yyyy`
  - `;time` → inserts current time formatted `hh:mm:ss tt`
- **Auto-elevate** — script attempts to auto-run elevated (Run *RunAs) when not started as administrator.
- **Game exclusions** — the script uses `#IfWinNotActive` to avoid interfering with certain games (e.g., `javaw.exe` (Minecraft), `valorant.exe`, `csgo.exe`).
- **Massive hotstring set** — ~**4960** hotstrings (auto-corrections, contractions, shorthand expansions, common phrases). These cover:
  - Common contractions and shorthand (`idk` → `I don't know`, `brb` → `be right back`, `ty` → `thank you`, etc.)
  - HTTP shortcuts (`http:\\\` → `http://`, `htp` → `http:`)
  - Spelling corrections (`accomodate` → `accommodate`, etc.)
  - Punctuation and small snippets
- **Tooltips and brief UI feedback** — toggles show `ToolTip` feedback and timers remove tooltips automatically.

---

## Shortcuts / Hotkeys (exact mappings found in the script)

- `F12`  
  Toggle full suspend mode (disables all hotkeys).
- `Win + Shift + Q` (`#+q`)  
  Prompt and exit script.
- `Win + Alt + Left` (`#!Left`)  
  Toggle LEFT AutoClick (uses `SetTimer LeftClick`).
- `Win + Alt + Right` (`#!Right`)  
  Toggle RIGHT AutoClick (uses `SetTimer RightClick`).
- `Insert`  
  If not paused, closes the active window (`WinGet` + `WinClose`).
- `Right Alt` (`RAlt`)  
  Toggle that sends `!w` (Alt+W) when toggled ON.
- `Right Ctrl` (`RControl`)  
  Sends `{Ctrl up}!{Tab}` — a quick app switch helper (releases Ctrl then does Alt+Tab).
- `Alt + WheelUp`  
  Volume up (mapped to `Volume_Up`).
- `Alt + WheelDown`  
  Volume down (mapped to `Volume_Down`).
- `Alt + Middle Mouse Button` (`Alt & MButton`)  
  Volume mute toggle.

Hotstrings of note:
- `;date` → inserts the date in `dd:MM:yyyy`.
- `;time` → inserts time in `hh:mm:ss tt`.
- `::http:\\\\::http://` and `::htp:::http:` — quick fixes/shortcuts for URLs.
- A very large set (~4960) of autocorrections, contractions, and common shorthand (e.g., `brb`, `idk`, `ty`, `dw`, many misspellings corrected to proper spelling).

---

## Installation / Usage

1. Install AutoHotkey (v1.x) if not already installed.
2. Place `Smart.ahk` in your preferred folder.
3. Run the script (double-click). If not started as admin, the script attempts to auto-elevate.
4. Use `F12` to suspend/resume all hotkeys. Use `Win+Shift+Q` to exit.
