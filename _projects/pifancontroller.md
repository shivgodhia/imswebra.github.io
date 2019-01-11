---
layout: project
title: Pi Fan Controller
date: 28 July 2018
screenshot:
  src: /assets/img/projects/pifancontroller/srcset@0,25x.jpg
  srcset:
    1920w: /assets/img/projects/pifancontroller/srcset@1x.jpg
    960w: /assets/img/projects/pifancontroller/srcset@0,5x.jpg
    480w: /assets/img/projects/pifancontroller/srcset@0,25x.jpg
accent_color: '#00baff'

caption: Temperature controlled CPU cooling
description: >
  A tiny script allowing temperature controlled Raspberry Pi cooling.

links:
  - title: Download
    url: https://github.com/imswebra/pifancontroller
---

This script is loosely based on work by Edoardo Paolo Scalafiotti found [here](https://hackernoon.com/how-to-control-a-fan-to-cool-the-cpu-of-your-raspberrypi-3313b6e7f92c)[^1], though this is a complete rewrite using the `gpiozero` library. It also makes use of two temperature variables (a minimum and a maximum), allowing the user to define a temperature *range* to oscillate within, avoiding rapid on/off switching when trying to stabilize around a single value.

Most small fans ([like this one](https://www.adafruit.com/product/3368)) are designed to be run off the Pi's 5V GPIO pins, however, there is no way to control this pins directly. Instead, we can use a transistor as a switch to turn on and off our fan. I personally used a NPN BJT with its base pin wired to [BCM pin 14](https://pinout.xyz/pinout/pin8_gpio14) (physical pin 8) and then used the ground and 5V power pins right beside it. Edoardo describes [something similar](https://hackernoon.com/how-to-control-a-fan-to-cool-the-cpu-of-your-raspberrypi-3313b6e7f92c#6021) is his write up as well, though I find pin 14 has much better positioning, plus has the benefit of being [pulled low by default](https://elinux.org/RPi_BCM2835_GPIOs), meaning your fan will not be spinning when the Pi is shutdown but still receiving power.

![Full-width image](/assets/img/projects/pifancontroller/wiring.png){:.lead}

To install the script, [download or clone](https://github.com/imswebra/pifancontroller) it from GitHub. When running locally, line 52 can be uncommented to help with debugging. User variables such as the temperature ranges and the check frequency are all easily available towards the top of the document.

To have to the script run on boot, add `python3 /path/to/pifancontroller.py &` to your [`rc.local`](https://www.raspberrypi.org/documentation/linux/usage/rc-local.md) file, making sure to include the ampersand to fork the process as the script runs in an infinite loop.


[^1]: Mirror available [here.](https://web.archive.org/web/20180604025525/https://hackernoon.com/how-to-control-a-fan-to-cool-the-cpu-of-your-raspberrypi-3313b6e7f92c)
