buriat-keyboard-xkb
===================

Modern XKB keyboard layout for the Buriat language, based on the original
2008 layout and updated for modern Linux desktop environments (Wayland/X11).


Overview
--------

This project provides a standalone Buriat keyboard layout (bua)
(not RU+AltGr), designed for correct UTF-8 input and long-term use in:

- UI localization
- documentation
- everyday typing
- development workflows

The layout is based on the original work created in 2008 by Dorzho Dugarov
and modernized in 2026 for current Linux desktop environments.


Features
--------

- Separate Buriat keyboard layout (bua)
- Native support for Buriat letters:
  - Ө ө
  - Ү ү
  - Һ һ
- Extended Cyrillic characters via Level3 (AltGr):
  - Ф ф
  - Ц ц
- Modern AltGr symbol layer:
  - @ # $ % … ^ & * [ ] < >
  - € £
- UTF-8 / Unicode compliant
- Compatible with:
  - Wayland
  - X11
  - GNOME
  - KDE Plasma
  - Xfce
- Designed as a foundation for Buriat UI localization and terminology work


Key combinations (AltGr)
------------------------

IMPORTANT:
All combinations refer to physical QWERTY keys.
Make sure the Buriat (bua) layout is active.


Letters
-------

AltGr + E        -> ф
Shift + AltGr + E -> Ф

AltGr + C        -> ц
Shift + AltGr + C -> Ц

AltGr + U        -> €
AltGr + A        -> £


Digits row
----------

AltGr + 2  -> @
AltGr + 3  -> №
Shift + AltGr + 3 -> #
AltGr + 4  -> $
AltGr + 5  -> %
AltGr + 6  -> …
Shift + AltGr + 6 -> ^
AltGr + 7  -> &
AltGr + 8  -> *
AltGr + 9  -> [
AltGr + 0  -> ]


Punctuation
-----------

AltGr + ISO <LSGT>        -> <
Shift + AltGr + ISO <LSGT> -> >


Keyboard layout diagram
-----------------------

Visual keyboard layout diagrams:

- docs/layout.svg
- docs/layout.png

(updated for v1.2)


## Repository Structure

```text
.
├── xkb/
│   ├── symbols/
│   │   └── bua
│   └── rules/
│       ├── evdev.lst
│       └── evdev.xml
├── legacy/
│   └── ver0.1/
│       └── bua
├── docs/
│   ├── layout.svg
│   └── layout.png
├── README.md
└── LICENSE

```
xkb/     - current, maintained layout files
legacy/  - original historical version (v0.1, 2008)
docs/    - documentation and layout diagrams


Installation (system-wide)
--------------------------

1. Copy layout files:

sudo cp xkb/symbols/bua /usr/share/X11/xkb/symbols/
sudo cp xkb/rules/evdev.* /usr/share/X11/xkb/rules/

2. Log out and log back in.

This is required for desktop environments to reload XKB layouts.


Usage
-----

Activate the layout:

setxkbmap -layout bua

Using multiple layouts (example):

setxkbmap -layout fi,bua -variant ,basic \
  -option "grp:win_space_toggle,level3(ralt_switch)"

Inspect the active layout:

setxkbmap -print -verbose 10


Troubleshooting
---------------

- After updating layout files, log out and log back in
- When using multiple layouts, ensure Buriat (bua) is active before testing AltGr
- On Wayland sessions, a full session restart may be required


Design principles
-----------------

- One language -> one layout
- No mixed RU+AltGr approach
- No dead keys for core alphabet
- Predictable, reproducible input for localization workflows


License
-------

This project is licensed under the MIT License.
See the LICENSE file for details.


Author
------

Original layout (2008):
Dorzho Dugarov

Modernization and maintenance (2026):
© Dorzho Dugarov, 2026
