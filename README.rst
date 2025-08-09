SPI NOR Tests 2025 Q3
=====================

Overview

This tiny project is planned to capture the needed details to connect a JEDEC complient, SPI NOR flash device to an NXP LPC55S69-EVK dev board.  Firmware choice is a Zephyr RTOS sample app.  As a first step a device tree overlay is needed to enable a SPI connected peripheral on the EVK board.

Mikroe click board header has a reset pin itself but this pin does not connect to any LPC55S69 pin.  Choose a general data pin on the Arduino header to use as an active low reset line to the flash device.  In given board's primary .dtsi file or device tree overly add something like::

 flash_n_reset: flash_n_reset {
     gpios = <&gpio0 0 GPIO_ACTIVE_LOW>;       
     is-output;
 };
