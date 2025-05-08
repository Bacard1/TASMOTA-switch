# 🤖 OLD "SONOFF" WITH NEW TASMOTA + HASS INTEGRATION

[![PayPal Donation](https://img.shields.io/badge/PayPal-Дари-синьо?logo=paypal)](https://www.paypal.com/donate/?hosted_button_id=AAWFZVF2XCP5A)
![Script](https://img.shields.io/badge/logo-yaml-green?logo=yaml)
[![Bulgarian](https://img.shields.io/badge/Български-език-green?logo=translate&labelColor=gray&style=flat-square&link=https://example.com/bg)](BG.md)

## 📦 Contents

- [🤖 OLD "SONOFF" WITH NEW TASMOTA + HASS INTEGRATION](#-old-sonoff-with-new-tasmota--hass-integration)
  - [📦 Contents](#-contents)
    - [🕷️ TASMOTA (Software):](#️-tasmota-software)
    - [⚙️ \[Sonoff BasicR2\]\[sonoff\]:](#️-sonoff-basicr2sonoff)
    - [🔗 \[AZDelivery TTL Serial Adapter\]\[azd\]](#-azdelivery-ttl-serial-adapterazd)
    - [💾 Drivers:](#-drivers)
    - [🧩 Installation:](#-installation)
  - [💊 Flashing Tool:](#-flashing-tool)
  - [💉 Firmware:](#-firmware)
  - [TASMOTA Integration and Configuration in Home Assistant:](#tasmota-integration-and-configuration-in-home-assistant)

---

### 🕷️ TASMOTA (Software):

Flashing SONOFF devices gives you full local control, and the ability to integrate them into Home Assistant ensures you won’t miss the cloud functionality they originally come with.

### ⚙️ [Sonoff BasicR2][sonoff]:

| ![Sonoff BasicR2](/IMG/BASICR2.png) | This is the device I will flash with TASMOTA, and the reasons are: <br> - *It takes too long to go from offline to online* <br> - *Huge delay when switching* <br> - *Often requires reconfiguration* |
|-----|-----|

> [!CAUTION]
> Before proceeding, disconnect the ["Sonoff BasicR2"][sonoff] from the power supply!!!

<br>

### 🔗 [AZDelivery TTL Serial Adapter][azd]

| ![AZDelivery TTL Serial Adapter](/IMG/TTL%20Adapter.png) | AZDelivery TTL Serial Adapter is the tool that will be used to connect, communicate, and flash the Sonoff BasicR |
|-----|-----|

### 💾 Drivers:

Before connecting, you need to install the following drivers: ["CP2102 drivers:"](https://www.silabs.com/products/development-tools/software/usb-to-uart-bridge-vcp-drivers), ["CH342, CH343, CH9102 drivers:"](https://www.wch.cn/downloads/CH343SER_ZIP.html), and ["CH340, CH341 drivers:"](https://www.wch.cn/downloads/CH341SER_ZIP.html). After installation, restart your operating system before proceeding.

### 🧩 Installation:

> [!CAUTION]
> Before continuing, make sure the ["Sonoff BasicR2"][sonoff] is disconnected from the power supply!!!

> [!NOTE]
> To connect the ["Sonoff BasicR2"][sonoff] to the ["AZDelivery TTL Serial Adapter"][azd], you will need access to the circuit board of the ["Sonoff BasicR2"][sonoff], meaning you’ll have to disassemble it!
>
> Check the wiring diagram in the image below!

<p align=center> 🆒WIRING DIAGRAM </p>

![Wiring Diagram](/IMG/sonoff-basicr2-modul.png)

> [!WARNING]
> Note that RX <--> TX are swapped. If you follow the diagram, you won’t have communication issues with the ["Sonoff BasicR2"][sonoff].

## 💊 Flashing Tool:

- [Tasmota Web Installer](https://tasmota.github.io/install/) - Flash Tasmota using a Chromium-based browser for ESP82xx and ESP32
- [Tasmotizer](https://github.com/tasmota/tasmotizer/releases) - Flashing and firmware download tool for ESP82xx only. (Windows, Linux, or Mac)
- [ESP-Flasher](https://github.com/Jason2866/ESP_Flasher) - GUI flasher for Tasmota based on ESPTOOL.py for ESP82XX and ESP32. (Windows, Linux, or Mac)
- [Esptool.py](https://github.com/espressif/esptool) - Official flashing tool from Espressif for ESP82xx and ESP32.

## 💉 Firmware:

Download the latest version of the file named ["tasmota.bin"](https://ota.tasmota.com/tasmota/release/)

For this project, I used the [Tasmota Web Installer](https://tasmota.github.io/install/), which doesn’t require manual firmware download. It offers a selection of firmware to choose from:

![demo Tasmota Web Installer](/IMG/TASMOTA-WEB.gif)

## TASMOTA Integration and Configuration in Home Assistant:

Installing this add-on is quite easy and is no different than installing any other Home Assistant add-on.

- Click the Home Assistant My button below to open the add-on in your Home Assistant instance.

[![TO ADD-ON](https://raw.githubusercontent.com/Bacard1/icon-set-project/9e7e05e78747dc0ecaa404a33cbe9e5d264ad003/button/button%20ADD-ON%20ON.svg)](https://my.home-assistant.io/redirect/supervisor_addon/?addon=a0d7b954_sonweb&repository_url=https%3A%2F%2Fgithub.com%2Fhassio-addons%2Frepository)

- Open the add-on in your Home Assistant instance.

- Click the "Install" button to install the add-on.

- Start the "TasmoAdmin" add-on.

- Check the "TasmoAdmin" logs to see if everything went smoothly.

- By default, the username is "admin" and the password is "password".

![TasmoAdmin](/IMG/TASMOTA.gif)

Integration is just as easy. Click the button below:

![ADDONS](/IMG/TASMOTA-Finish.gif)

[![TO INTEGRATION](https://raw.githubusercontent.com/Bacard1/icon-set-project/9e7e05e78747dc0ecaa404a33cbe9e5d264ad003/button/button%20ADD%20INTEGRATION%20TO.svg)](https://my.home-assistant.io/redirect/config_flow_start?domain=tasmota)

> [!NOTE]
> This integration will fully connect Home Assistant to all devices added via the TASMOTA add-on. Restart Home Assistant and enjoy full control of your devices.

> [!TIP]
> If you liked this project, you can find more interesting projects made by me [HERE](https://github.com/Bacard1?tab=repositories).<br>
> If you have any difficulties or questions, don’t hesitate to contact me.
