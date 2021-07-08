# LTP-305 Breakout Garden dual 5x7 LED matrix driver for Raspberry Pi Pico

## Overview

This driver is a hastily hacked-together version of [Pimironi's original driver](https://github.com/pimoroni/ltp305-python) 
that removes the reliance on the `smbus` library. Instead, this version makes use of the Pico's `machine.I2C` package to
drive the breakout board.

## Usage
[Micropython](https://github.com/micropython/micropython) projects cannot import external libraries PIP-style (or at
least not to my knowledge), so copy the `ltp305` folder into your project and refer to it directly from your project's
other Python files e.g.

    from ltp305 import LTP305

Initialisation is a bit different from the Pimoroni driver as `I2C` needs to be told what pins to use. The defaults are
pins `0` and `1`, but this can be changed when creating the `LTP305` object using the `sda_pin` and `scl_pin` arguments.

## Examples
The original @pimoroni [examples](https://github.com/pimoroni/ltp305-python/tree/master/examples) should still work
exactly the same with this new driver.