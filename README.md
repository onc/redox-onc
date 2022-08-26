# redox-onc

My redox keyboard layout.

Key features:

- Simple
- A modern space cadet bindings
  - Left `Shift` => Left `Shift` or `(` when pressed on its own
  - Right `Shift` => Right `Shift` or `)` when pressed on its own
  - `Caps Lock` => `Ctrl` or `Esc` when pressed on its own 
- German umlauts (ä, ü, ö, ß) using Mode 1 + (a, u, o, s)

![](https://github.com/onc/redox-onc/blob/main/layout/onc_layer_0.png)
![](https://github.com/onc/redox-onc/blob/main/layout/onc_layer_1.png)

## Setup

- Install qmk as described [here](https://docs.qmk.fm/#/newbs_getting_started).
- Create a keymap folder
  ```
  cd /path/to/qmk_firmware/keyboards/redox/keymaps
  mkdir onc
  cd onc
  ```
- Copy `onc.json` and `config.h` to the keymap folder
- Generate `keymap.c`: `qmk json2c onc.json > keymap.c`

## Flash

I have an arduino in my left and an elite-c microcontroller in the right hand.

```
cd /path/to/qmk_firmware
# left hand (arduino)
make redox/rev1/base:onc:avrdude-split-left
# right hand (elite-c)
make redox/rev1/base:onc:dfu-split-right
```
