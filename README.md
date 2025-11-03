# Karabiner Config AI made README

*IMPORTANT*: virtual keyboard should be in ANSI, this was made for a logitech ANSI keyboard and a mac ISO keyboard.
This configuration defines several **device-specific keyboard remappings** for both the **Apple internal keyboard** and the **Logitech G815** keyboard. It’s designed to make both behave more consistently with macOS shortcuts and usability preferences.

---

## 📦 Overview

**File name:** `karabiner.json`
**Profile name:** `Default profile`
**Keyboard type:** ANSI
**Custom parameters:**

* `to_if_alone_timeout_milliseconds`: 250 ms
* `to_if_held_down_threshold_milliseconds`: 400 ms

---

## 🧠 Summary of Rules

### 1. Apple Internal Keyboard — `non_us_backslash → grave_accent_and_tilde`

**Description:** Fixes the behavior of the `non_us_backslash` key on Apple internal keyboards (usually next to the left Shift key).

* **Shift + non_us_backslash → Shift + `grave_accent_and_tilde`** (`~`)
* **non_us_backslash → `grave_accent_and_tilde`** (`` ` ``)

**Device filter:** Apple internal keyboard (`vendor_id: 1452`, `product_id: 833`)

---

### 2. Apple Internal Keyboard — Swap `fn` and `command`

**Description:** Switches the functionality of the `fn` and `⌘` (Command) keys.

* `fn → left_command`
* `left_command → fn`

**Device filter:** Apple internal keyboard (`vendor_id: 1452`, `product_id: 833`)

---

### 3. Logitech G815 — macOS-friendly layout

**Description:** Adapts the Logitech G815 keyboard for macOS conventions and adds custom productivity shortcuts.

**Device filter:** Logitech G815 (`vendor_id: 1133`, `product_id: 49983`)

#### Key remappings:

| Original Key | Remapped To | Notes                             |
| ------------ | ----------- | --------------------------------- |
| Left Ctrl    | ⌘ Command   | macOS-style shortcut alignment    |
| Left Win     | Ctrl        | Swaps position for consistency    |
| Right Win    | ⌘ Command   |                                   |
| Menu         | Fn          | Enables access to function layers |
| Home         | ⌘ + ←       | Moves to line start (macOS style) |
| End          | ⌘ + →       | Moves to line end (macOS style)   |

#### Special key: `Insert`

* **Short press:** ⌘ + D → *Mute in Google Meet*
* **Hold:** ⌘ + ⇧ + A → *Toggle audio in Zoom or Teams*

---

### 4. Logitech G815 — `⌥ =` → F18

**Description:** Allows triggering a virtual F18 key with `Option + =`.
This can be used as a custom hotkey trigger in automation tools like **BetterTouchTool**, **Keyboard Maestro**, or **Hammerspoon**.

**Device filter:** Logitech G815 (`vendor_id: 1133`, `product_id: 49983`)

---

### 5. Apple Internal Keyboard — `⌥ =` → F18

**Description:** Same as above but applied to the MacBook’s internal keyboard.

**Device filter:** Apple internal keyboard (`vendor_id: 1452`, `product_id: 833`)

---

## ⚙️ How to Use

1. **Install [Karabiner-Elements](https://karabiner-elements.pqrs.org/).**
2. Open **Karabiner-Elements → Complex Modifications → Add Rule**.
3. Click **“Import more rules from file…”** and select this `karabiner.json`.
4. Ensure the profile **“Default profile”** is selected.
5. Reconnect your keyboards if necessary.

---

## 🧩 Compatibility Notes

* The configuration differentiates between devices using **`vendor_id`** and **`product_id`**:

  * Apple Internal Keyboard: `vendor_id: 1452`, `product_id: 833`
  * Logitech G815: `vendor_id: 1133`, `product_id: 49983`
* Rules only apply when those specific devices are active.
* The `Insert` key’s dual behavior relies on Karabiner’s **“to_if_alone”** and **“to_if_held_down”** timing parameters.

---

