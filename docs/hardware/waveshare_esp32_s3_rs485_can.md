---
title: "Waveshare ESP32‐S3‐RS485‐CAN"
---

## Hardware basics

The Waveshare ESP32-S3-RS485-CAN is an affordable and easy to source board. It supports 1x CAN channel, and 1x RS485 port. It comes with a DIN mountable case, and accepts an input voltage between 7-36V.

![image](../images/waveshare-esp32-s3-rs485-can-01.png)

### Where this hardware shines

On setups that require RS485, and have CAN controlled contactors (E.g. Tesla Battery with a Fronius inverter), it's a plug and play solution. This board is a more future proof alternative compared to the LilyGo T-CAN485.

## Purchase link

The hardware can be bought via sites like AliExpress, or the official [Waveshare](https://www.waveshare.com/esp32-s3-rs485-can.htm) shop.

## Limitations

This board has a single CAN channel and single RS485 port. The 4-pin SH1.0 connector on the board exposes GPIO1 and GPIO2, which can be configured in firmware settings as either a status LED or an I2C display (see below).

Internal header exposes pins to be used for GPIO controlled contactors and an additional CAN interface.

!!! info "IMPORTANT"
    You can build a maximum [double battery](../setup/software/battery_2x.md) setup with this unit when used with an RS485 inverter, using its onboard CAN and a [second CAN interface](../setup/can_related/can_fd_add_on_mcp2518fd.md), as this will mostly max out the available GPIOs on the internal pin header. No way to add a third CAN interface to this board.

The plastic case has a bit of a headroom above the USB-C socket which allows for a small cutout to lead the cables from the header:

<img width="850" height="716" alt="kép" src="https://github.com/user-attachments/assets/e30648d4-7e2a-4227-805e-0a043c9d79ce" />

<img width="850" height="716" alt="kép" src="https://github.com/user-attachments/assets/ddf21b38-d2b6-4be7-bd29-0a5d4ab44f1c" />

A Waveshare ESP32-S3-RS485-CAN with a [second CAN interface](../setup/can_related/can_fd_add_on_mcp2518fd.md) and external contactors control for a [double battery](../setup/software/battery_2x.md) setup:

<img width="1060" height="744" alt="kép" src="https://github.com/user-attachments/assets/86792a4b-a483-4394-9c99-73be8e2d1274" />

## Optional accessories

### Expansion header

The board has pads for a 20-pin **2.0mm** pitch pin header.

![image](../images/waveshare-esp32-s3-rs485-can-04.png){ width="551" height="449" }

Socket for own soldering: [Aliexpress](https://www.aliexpress.com/item/4000597517515.html)
Pigtail cable: [Aliexpress](https://www.aliexpress.com/item/1005009728347159.html)

Choose the 2x10p version!

### Status LED (NeoPixel via GPIO2)

The 4-pin SH1.0 connector (located directly behind the USB C connector) can power an optional **Adafruit NeoPixel** (or any WS2812-compatible single LED) connected to GPIO2, providing a visual status indicator.  Please note that the Waveshare only outputs 3.3v!

![Waveshare to NeoPixel wiring diagram](../images/waveshare-esp32-s3-rs485-can-02.png){ width="800" height="599" }

Once wired, open the **Settings** page in the web interface and set **GPIO 1/2 function** to **Status LED** (this is the default).

![Waveshare_settings](../images/waveshare-esp32-s3-rs485-can-03.png){ width="792" height="374" }

### I2C Display (SSD1306 via GPIO1 + GPIO2)

The same connector can alternatively drive an **SSD1306 128×64 I2C OLED display**, using GPIO1 as SDA and GPIO2 as SCL.

In the **Settings** page, set **GPIO 1/2 function** to **I2C Display (SSD1306)** to enable this.

!!! note "NOTE"
    The status LED and I2C display are mutually exclusive — only one can be active at a time.

### See also

- [BOOT button](../setup/software/boot_button_functions.md) for special features to enable AP, wipe wifi settings or factory reset the device
- [CAN add-on MCP2518FD](../setup/can_related/can_fd_add_on_mcp2518fd.md) for an additional CAN interface

