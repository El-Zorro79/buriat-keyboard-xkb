# buriat-keyboard-xkb
Modern XKB keyboard layout for the Buriat language, based on the original 2008 layout and updated for Wayland, GNOME, KDE, and Xfce.

# Buriat Keyboard Layout (XKB)

Modern XKB keyboard layout for the **Buriat language**.

This project provides a **standalone Buriat keyboard layout** (not RU+AltGr),
designed for correct UTF-8 input and long-term use in UI localization,
documentation, and everyday typing.

The layout is based on the original work created in 2008 by Dorzho Dugarov
and has been modernized by Dorzho Dugarov for current Linux desktop environments.

---

## Features

- Separate Buriat keyboard layout (`bua`)
- Native support for Buriat letters:
  - Ө ө
  - Ү ү
  - Һ һ
- UTF-8 / Unicode compliant
- Compatible with:
  - Wayland
  - X11
  - GNOME
  - KDE Plasma
  - Xfce
- Designed as a foundation for Buriat UI localization and terminology work

---

## Repository Structure

.
├── xkb/
│ ├── symbols/
│ │ └── bua
│ └── rules/
│ ├── evdev.lst
│ └── evdev.xml
├── legacy/
│ └── ver0.1/
│ └── bua
├── docs/
│ └── layout.png
├── README.md
└── LICENSE


- `xkb/` — current, maintained layout files
- `legacy/` — original (historical version) (v0.1, 2008)
- `docs/` — documentation and layout diagrams

---

Installation (system-wide)

```bash

1. Copy layout files

sudo cp xkb/symbols/bua /usr/share/X11/xkb/symbols/
sudo cp xkb/rules/evdev.* /usr/share/X11/xkb/rules/

2. Log out and log back in

This is required for desktop environments to reload XKB layouts.
Usage

You can activate the layout via system settings
or manually for testing:

setxkbmap -layout bua

To inspect the active layout:

setxkbmap -print -verbose 10

Design Principles

    One language → one layout

    No mixed RU+AltGr approach

    No dead keys for core alphabet

    Predictable, reproducible input for localization workflows

License

This project is licensed under the MIT License.
See the LICENSE
file for details.
Author

Original layout (2008):
Dorzho Dugarov

Modernization and maintenance (2026):
©Dorzho Dugarov, 2026
