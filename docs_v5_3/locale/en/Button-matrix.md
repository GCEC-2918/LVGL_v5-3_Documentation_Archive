_Written for v5.1_

## Overview

The Button Matrix objects can display **multiple buttons** according to a descriptor string array, called _map_. You can specify the map with `lv_btnm_set_map(btnm, my_map)`. 

The **declaration of a map** looks like `const char * map[] = {"btn1", "btn2", "btn3", ""}`. Note that **the last element has to be an empty string**!  

The first character of a string can be a **control character** to specify some attributes:

- **bit 7..6** Always _0b10_ to differentiate the control byte from the textual characters
- **bit 5** Inactive button
- **bit 4** No long press for the button
- **bit 3** Hidden button
- **bit 2..0** Relative width compared to the buttons in the same row. [1..7]

It is recommended to specify the **control byte as an octal number**. For example `"\213button"`. The octal number always starts with _2_ (bit 7..6) the middle part is the attributes (bit 5..3) and the last part is the width (bit 2..0). So the example describes a 3 unit wide, hidden button.

Use "\n" in the map  to make **line break**: `{"btn1", "btn2", "\n", "btn3", ""}`. The button's width is recalculated in every line.

The `lv_btnm_set_action(btnm, btnm_action)` specifies an action to call when a button is released. 

You can enable the **buttons to toggle** when they are clicked. There can only be one toggled button at a time. The `lv_btnm_set_toggle(btnm, true, id)` enables the toggling and sets the _id_th button to the toggled state.

## Style usage

The Button matrix works with 6 styles: a background and 5 button styles for each states. You can set the styles with `lv_btnm_set_style(btn, LV_BTNM_STYLE_..., &style)`. The background and the buttons use the _style.body_ properties. The labels use the _style.text_ properties of the button styles.

- **LV_BTNM_STYLE_BG** Background style. Uses all _style.body_ properties including _padding_ Default: _lv_style_pretty_
- **LV_BTNM_STYLE_BTN_REL** style of the released  buttons. Default: _lv_style_btn_rel_
- **LV_BTNM_STYLE_BTN_PR** style of the pressed buttons. Default: _lv_style_btn_pr_
- **LV_BTNM_STYLE_BTN_TGL_REL** style of the toggled released  buttons. Default: _lv_style_btn_tgl_rel_
- **LV_BTNM_STYLE_BTN_TGL_PR** style of the toggled pressed  buttons. Default: _lv_style_btn_tgl_pr_
- **LV_BTNM_STYLE_BTN_INA** style of the inactive  buttons. Default: _lv_style_btn_ina_

## Notes

- The Button matrix object is **very light weighted**. It creates only the Background Base object and draws the buttons on it instead of creating a lot of real button.

## Example
![Button matrix image](http://docs.littlevgl.com/img/button-matrix-lv_btnm.png)
```c
```
