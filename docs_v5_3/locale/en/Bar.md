_Written for v5.1_

## Overview

The Bar objects have got two main parts: a **background** which is the object itself and an **indicator** which shape is similar to the background but its width/height can be adjusted. 

The orientation of the bar can be **vertical or horizontal** according to the width/height ratio. Logically on horizontal bars the indicator width, on vertical bars the indicator height can be changed. 

A **new value** can be set by: `lv_bar_set_value(bar, new_value)`. The value is interpreted in **range** (minimum and maximum values) which can be modified with: `lv_bar_set_range(bar, min, max)`. The default range is: 1..100.

The setting of a new value can happen with an **animation** from the current value to the desired. In this case use `lv_bar_set_value_anim(bar, new_value, anim_time)`.

## Style usage

- **background** is a [[Base object]]therefore it uses its style elements. Its default style is: `LV_STYLE_PRETTY`.  
- **indicator** is similar to the background. Its styles can be set by: `lv_bar_set_style_indic(bar,&style_indic)`. It uses the _hpad_ and _vpad_ style elements to keep space from the background. Its default style is: `LV_STYLE_PRETTY_COLOR`.

## Notes

- The indicator is not a real object; it is only drawn by the bar.

## Example

![Bar image](http://docs.littlevgl.com/img/bar-lv_bar.png)

```c

```
