# NM-CYD-C5

English | [中文](README_zh.md)

NM-CYD-C5 is a Cheap Yellow Display (CYD) based on ESP32-C5, supporting dual-band Wi-Fi 6 / BLE 5 / Thread / Zigbee.

This development board features an ESP32-C5 with a built-in 320 × 240 2.8" LCD touchscreen, similar to the [ESP32-Cheap-Yellow-Display](https://github.com/witnessmenow/ESP32-Cheap-Yellow-Display). The default LCD driver is ST7789, and it can also be changed to the ILI9341 driver.

# Features

The NM-CYD-C5 has the following features:

- ESP32-C5-WROOM-1, 16MB Flash and 8MB PSRAM
- 320 × 240 LCD Display (2.8")
- Resistive Touch Screen
- ESP32-C5 USB Type-C port and USB Type-C to UART port (CH340), for powering and programming
- SD Card Slot, RGB LED and some additional pins
- Fully compatible dimensions and interfaces with ESP32-Cheap-Yellow-Display, enabling seamless replacement
- FPC connector added for more convenient connection to external modules

## New Features of ESP32-C5

- ESP32-C5 RISC-V 32-bit @ 240 MHz
- Dual-Band Wi-Fi 6: 2.4GHz & 5GHz (802.11ax)
- Bluetooth 5: Classic and BLE 5 with SPP, HID, GATT support
- IEEE 802.15.4: Zigbee 3.0 end-device support
- Thread: IPv6-based mesh networking protocol

| Component | Specification |
|:---:|:---:|
| **Main SoC** | ESP32-C5 (RISC-V 32-bit, 240MHz) |
| **Wireless Protocols** | Wi-Fi 6 (802.11ax) 2.4/5GHz + BLE 5.3 + IEEE 802.15.4 |
| **Display** | 2.8" TFT, 240×320, ST7789, Touch Screen |
| **Memory** | 16MB Flash + 8MB PSRAM |
| **Interface** | 2× USB-C, GPIO, Micro SD Card Slot |

# Where to Buy

You can get the NM-CYD-C5 from the RockBase IoT AliExpress store, the RockBase IoT official website, or from NMTech Stores.

- [RockBase IoT Store](https://www.aliexpress.com/store/1105401362)
- [RockBase Shop](https://rockbase.shop/products/nm-cyd-c5)
- [NMTech Global Store](https://www.aliexpress.com/store/1104265822)
- [NMMiner](https://www.nmminer.com)

# Getting Started with Your NM-CYD-C5

For details on how to get started with your NM-CYD-C5, please check out the [Setup and Configuration](https://wiki.rockbaseiot.com/en/docs/products/nm-cyd-c5/) page.

To work with NM-CYD-C5, you should use the newest espressif32 library, version 3.3.5 or higher.

```ini
[env]
platform = https://github.com/pioarduino/platform-espressif32/releases/download/55.03.36/platform-espressif32.zip ; Arduino 3.3.6
```

When you use TFT_eSPI to work with the LCD, you should add `TFT_eSPI_ESP32_C5.c/h` to the Processors directory, and update `TFT_eSPI.c/h` with `CONFIG_IDF_TARGET_ESP32C5`.
These files can be found in `Demos\Arduino\libraries\TFT_eSPI`.

## Pinout of NM-CYD-C5

### Using ST7789 with XPT2046 for Touchscreen, Shared SPI

| Device | SCK | MISO | MOSI | CS | IRQ |
| --- | :---: | :---: | :---: | :---: | :---: |
| Display | 6 | 2 | 7 | 23 | --- |
| Touch | 6 | 2 | 7 | 1 | --- |
| SD Card | 6 | 2 | 7 | 10 | --- |

### LP-UART (`NM-CYD-C5:P5`) for GPS Module, e.g. `NM-ATGM336H`, Plug and Play

| Device | RX | TX | GPIO |
| --- | :---: | :---: | :---: |
| GPS | 4 | 5 | --- |

### Extend IO for I2C, `NM-CYD-C5: CN1`

| 1 | 2 | 3 | 4 |
|---|---|---|---|
| 3.3V | IO9 | IO8 | GND |

### Extend IO, `NM-CYD-C5: P1`

| 1 | 2 | 3 | 4 |
|---|---|---|---|
| IO4 | IO8 | IO26 | GND |

### NM Extend IO: 12-Pin FPC Interface, `NM-CYD-C5: FPC2`

| 1 | 2 | 3 | 4 | 5 | 6 | 7 | 8 | 9 | 10 | 11 | 12 |
|---|---|---|---|---|---|---|---|---|---|---|---|
| IO2 | IO6 | IO7 | IO10 | GND | IO4 | IO8 | IO5 | IO9 | USB D- | USB D+ | GND |

### WS2812 LEDC and Screen Backlight

| NM-CYD-C5 | Pin |
| :------: | :---: |
| IO25 | Display BL |
| IO27 | WS2812 RGB LED |

![NM-CYD-C5-Pinout](Documention/pics/nm-cyd-c5-pinout.jpg)

![NM-CYD-C5 detail](Documention/pics/nm-cyd-c5-detail.jpg)

## The NM-CYD-C5 Colorful Special Edition

The [RockBase IoT Colorful Special Edition](https://rockbase.shop/products/nm-cyd-c5-colorful) will be released soon and is compatible with the standard NM-CYD-C5.

![NM-CYD-C5-Color](Documention/pics/nm-cyd-c5-color.jpg)

![NM-CYD-C5-Colorful](Documention/pics/nm-cyd-c5-colorful.png)

## The NM-CYD-C5 External Antenna Board

In response to widespread user demand, the latest batch of NM-CYD-C5-Colorful includes a new external-antenna design, available as an option. The NM-CYD-C5-Colorful-Ant comes with an IPEX 1 cable and a dual-band 2.4G/5G antenna, making it easy to use an external antenna. The external-antenna version of the NM-CYD-C5-Colorful delivers better Wi-Fi and BLE signal reception, making it suitable for users with higher wireless-performance requirements.

![NM-CYD-C5-Colorful-Antenna](Documention/pics/nm-cyd-c5-colorful-ant.png)

### External Antenna Parameters

- Frequency range: 2400~2500MHz / 5000~5800MHz
- VSWR: 2400-2500 ≤ 2.5, 5000-5800 ≤ 2.5
- Efficiency %: 2400-2500: 83.3 AVG; 5000-5800: 73.8 AVG
- Peak Gain (dBi): 2400-2500: 3.2 AVG; 5000-5800: 3.7 AVG
- Radiation Properties: Omni-directional
- Polarization: Linear

## Compare with ESP32-2432S028

| Feature | Standard CYD (ESP32) | NM-CYD-C5 |
| :---: | :---: | :---: |
| **Wi-Fi Band** | 2.4GHz | 2.4+5GHz |
| **Wi-Fi Standard** | 802.11 b/g/n | 802.11ax (Wi-Fi 6) |
| **ZigBee** | None | ZigBee 3.0 |
| **Thread** | None | Thread 1.3 |
| **Flash** | 4MB | 16MB |
| **PSRAM** | None | 8MB |

![](Documention/pics/compare_cyd-2.jpg)

![](Documention/pics/compare-cyd-c5.jpg)

# Supported Projects

## Already Supported Projects

- [NMMiner](https://github.com/NMminer1024/NMMiner)
- [Brucefw](https://github.com/BruceDevices/firmware)
- [ESP32Marauder](https://github.com/RockBase-iot/ESP32Marauder)
- [Rogue-Radar](https://github.com/RockBase-iot/Rogue-Radar-CYD)

    Rogue Radar is a handheld ESP32 firmware that combines multiple wireless and utility tools into one rotary-driven interface.

- [CYM (Cheap Yellow Monster)](https://github.com/JimGat/CYM-NM28C5)

    Cheap Yellow Monster is a portable, touchscreen-driven WiFi security toolkit running on the NM-CYD-C5.

- [Launcher](https://github.com/RockBase-iot/Launcher)

    Application launcher for M5Stack, Lilygo, CYDs, Marauder and ESP32 devices.

- [ESP-Claw](https://github.com/espressif/esp-claw)

    ESP-Claw is Espressif's chat-coding AI agent framework for IoT devices. It defines device behavior through conversation and completes the full loop of sensing, decision-making, and execution locally on Espressif chips. Inspired by the OpenClaw concept and reimplemented in C, ESP-Claw is lightweight, intelligent, and continuously evolving.

    ![](Documention/pics/esp-claw.png)

    *New Version Released*: ESP-Claw 0.3.0 has been updated to support NM-CYD-C5, merging new features from `espressif/master`.

If you just want to flash the firmware, you can try the [RockBase IoT Web Flasher](https://flash.rockbaseiot.com) and choose device type `nm-cyd-c5`.

If you would like your firmware or project to run on the NM-CYD-C5, please contact the RockBase IoT team and we will assist you with adaptation and testing.

For firmware you would like to offer as a download on our Web Flasher, please check out the [ESPWebApps](https://github.com/RockBase-iot/ESPWebApps) project. ESPWebApps is a web application management platform based on ESP32 that allows users to run and manage multiple web applications on the ESP32. With ESPWebApps, you can easily share your projects with NM-CYD-C5 users, making it simple to download, install, update, and run applications on the NM-CYD-C5.

## Ongoing Projects

- [HaleHound-CYD](https://github.com/JesseCHale/HaleHound-CYD)
- [ESP32-KillerBee](https://github.com/RockBase-iot/ESP32-KillerBee)
- [ESP32DualBandWardriver](https://github.com/justcallmekoko/ESP32DualBandWardriver)
