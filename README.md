# redox
QMK layout for redox

config.qmk.fm - keyboard configurator

https://docs.qmk.fm/#/feature_tap_dance
https://docs.qmk.fm/#/keycodes

Added some tapdance magic for home/pgdown end/pgup


## Installation
git clone https://github.com/szwl/redox.git qmk_firmware/keyboards/redox/keymaps/szwl-2

## Tap Dance Declarations
```C
enum {
  TD_HOME_PGD = 0,
  TD_END_PGUP = 1
};

//Tap Dance Definitions
qk_tap_dance_action_t tap_dance_actions[] = {
  //Tap once for End, twice for page down
  [TD_HOME_PGD]  = ACTION_TAP_DANCE_DOUBLE(KC_HOME, KC_PGDN),
  [TD_END_PGUP]  = ACTION_TAP_DANCE_DOUBLE(KC_END, KC_PGUP)
// Other declarations would go here, separated by commas, if you have them
};

//use as keycodes:
TD(TD_HOME_PGD)
TD(TD_END_PGUP)
```

## Flashing
make redox/rev1:szwl-2:avrdude

