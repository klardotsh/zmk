---
title: Mouse Emulation Behaviors
sidebar_label: Mouse Emulation
---

## Summary

Mouse emulation behaviors send mouse events. Currently, only mouse button presses are supported, but movement
and scroll action support is planned for the future.

## Configuration Option

This feature can be enabled via a config option:

```
CONFIG_ZMK_MOUSE=y
```

If you use the mouse key press behavior in your keymap, the feature will automatically be enabled for you.

## Mouse Button Defines

To make it easier to encode the HID mouse button numeric values, include
the [`dt-bindings/zmk/mouse.h`](https://github.com/zmkfirmware/zmk/blob/main/app/include/dt-bindings/zmk/mouse.h) header
provided by ZMK near the top:

```
#include <dt-bindings/zmk/mouse.h>
```

Doing so allows using a set of defines such as `LCLK` and `RCLK` with these behaviors.

## Mouse Button Press

This behavior can press/release up to 5 mouse buttons.

### Behavior Binding

- Reference: `&mkp`
- Parameter: A `uint8` with bits 0 through 4 each referring to a button.

### Examples

The following will send a left click press when the binding is triggered:

```
&mkp LCLK
```

This example will send press of the fourth mouse button when the binding is triggered:

```
&mkp MB4
```
