_Written for v5.1, revision 2_

## Overview

Buttons can react on user **press**, **release** or **long press** via callback functions (`lv_action_t` function pointers). You can set the callback functions with: `lv_btn_set_action(btn, ACTION_TYPE, callback_func)`. The possible action types are:

- LV_BTN_ACTION_CLICK: the button is released after pressing (clicked) or, when using keypad, after the key `LV_GROUP_KEY_ENTER` is released
- LV_BTN_ACTION_PR: the button is pressed
- LV_BTN_ACTION_LONG_PR: the button is long pressed
- LV_BTN_ACTION_LONG_PR_REPEAT: the button is long pressed and this action is triggered periodically

Buttons can be in one of the **five possible states**:

- LV_BTN_STATE_REL Released state
- LV_BTN_STATE_PR Pressed state
- LV_BTN_STATE_TGL_REL Toggled released state (On state)
- LV_BTN_STATE_TGL_PR Toggled pressed state (On pressed state)
- LV_BTN_STATE_INA Inactive state

The buttons can be configured as **toggle button** with `lv_btn_set_toggle(btn, true)`. In this case on release, the button goes to toggled released state.

You can set the button's state manually by: `lv_btn_set_state(btn, LV_BTN_STATE_TGL_REL)`.

A button can go to **Inactive state** only manually (by _lv_btn_set_state()_). In an Inactive state, none of the action will be called.  

Similarly to [Containers](/Container) buttons also have **layout** and **auto fit**:

- `lv_btn_set_layout(btn, LV_LAYOUT_...) `set a layout. The default is LV_LAYOUT_CENTER. So if you add a label then it will be automatically aligned to the middle.
- `lv_btn_set_fit(btn, hor_en, ver_en)` enables to set the button width and/or height automatically according to the children.

## Style usage

A button can have 5 independent styles for the 5 state. You can set them via: `lv_btn_set_style(btn, LV_BTN_STYLE_..., &style)`. The styles use the _style.body_ properties.

- **LV_BTN_STYLE_REL** style of the released state. Default: _lv_style_btn_rel_
- **LV_BTN_STYLE_PR** style of the pressed state. Default: _lv_style_btn_pr_
- **LV_BTN_STYLE_TGL_REL** style of the toggled released state. Default: _lv_style_btn_tgl_rel_
- **LV_BTN_STYLE_TGL_PR** style of the toggled pressed state. Default: _lv_style_btn_tgl_pr_
- **LV_BTN_STYLE_INA** style of the inactive state. Default: _lv_style_btn_ina_

## Notes

- If a button is dragged its click and long press action will not be called
- If a button was long pressed and its long press action was set then its click action will not be called

## Example
![Button image](http://docs.littlevgl.com/img/button-lv_btn.png)
```c

```
