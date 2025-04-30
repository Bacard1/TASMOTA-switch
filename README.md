# 🤖 OLD "SONOFF" WITH A NEW TASMOTA + HASS INTEGRATION

[![PayPal дарение](https://img.shields.io/badge/PayPal-Дари-синьо?logo=paypal)](https://www.paypal.com/donate/?hosted_button_id=AAWFZVF2XCP5A)
![Скрипт](https://img.shields.io/badge/logo-yaml-green?logo=yaml)

## 📦 Table of Contents

- [🤖 OLD "SONOFF" WITH A NEW TASMOTA + HASS INTEGRATION](#-old-sonoff-with-a-new-tasmota--hass-integration)
  - [📦 Table of Contents](#-table-of-contents)
    - [🕷️ TASMOTA (софтуер):](#️-tasmota-софтуер)
    - [⚙️ Sonoff BasicR2:](#️-sonoff-basicr2)
    - [🔗 AZDelivery TTL Serial Adapter](#-azdelivery-ttl-serial-adapter)
    - [💾 Drivers:](#-drivers)
    - [🧩 Installation:](#-installation)
  - [💊 Flashing Tool:](#-flashing-tool)
  - [💉 Firmware:](#-firmware)
  - [Tasmota integration and configuration into Home Assistant:](#tasmota-integration-and-configuration-into-home-assistant)

---

### 🕷️ TASMOTA (софтуер):

The Flush of Sonoff devices is the solution for a full cotrol over it in local mode, and the ability to be integrated into Home Assistant takes care of not missing the cloud mode with which Sonoff is sold.

### ⚙️ [Sonoff BasicR2][sonoff]: 

| ![Sonoff BasicR2](/IMG/BASICR2.png) | This is the device that will flap with "tasmota" and the reasons are: <br> - *The passage of the offline to Onlyin takes a lot of time *<br> - *thunder Latin when switching *<br> - *often requires configuration of a new*|
|-----|-----|

> [!CAUTION]
> Before proceeding, turn off ["Sonoff Basicr2"][sonoff] from the electrical network !!!

<br>

### 🔗 [AZDelivery TTL Serial Adapter][azd]

| ![AZDelivery TTL Serial Adapter](/IMG/TTL%20Adapter.png) | Azdelivery TTL Serial Adapter is the tool that will demonstrate to connect, read and flash ["Sonoff BasicR2"][sonoff] |
|-----|-----|

### 💾 Drivers:

Before connecting, it is necessary to install drivers ["CP2102 drivers:"](https://www.silabs.com/products/development-tools/software/usb-to-uart-bridge-vcp-drivers) ["CH342, CH343, CH9102 drivers:"](https://www.wch.cn/downloads/CH343SER_ZIP.html) и ["CH340, CH341 drivers:"](https://www.wch.cn/downloads/CH341SER_ZIP.html). After installing them, you need to restart the operating system before continuing.

### 🧩 Installation:

> [!CAUTION]
> Before continuing, make sure that the Sonoff Basicr2] [SONOFF] is excluded from the mains !!!

> [!NOTE]
> To connect ["SONOFF BASICR2"][sonoff] with ["Azdelivery TTL Serial Adapter"][azd], you will need to get to the card of ["Sonoff Basicr2"][sonoff], this means that you have to disassemble it!
> Look at the circuit of the connection in the image below !!!

<p align=center> 🆒Connection scheme </p>

![Connection scheme](/IMG/sonoff-basicr2-modul.png)

> [!WARNING]
> Note that RX <-> TX are exchanged.If you stick to the scheme, then you will have no problems with communication with ["Sonoff BasicR2"][sonoff].

## 💊 Flashing Tool:

- [Tasmota Web Installer](https://tasmota.github.io/install/) - Flash Tasmota using a chrome -based browser for ESP82XX and ESP32
- [Tasmotizer](https://github.com/tasmota/tasmotizer/releases) - Firmware Flashing and Download only for ESP82XX. (Windows, Linux or Mac)
- [ESP-Flasher](https://github.com/Jason2866/ESP_Flasher) - Gui Flasher for Tasmota based on ESPTOOL.py for ESP82XX and ESP32. (Windows, Linux or Mac)
- [Esptool.py](https://github.com/espressif/esptool) - The official flashing tool from ESPRESFIF for ESP82XX and ESP32.

## 💉 Firmware: 

Download the latest version of the file with a name["tasmota.bin"](https://ota.tasmota.com/tasmota/release/)

I used for this project [Tasmota Web Installer](https://tasmota.github.io/install/), It does not have to draw Firmware.It hasгама от Firmware от който да избирате.:

![demo Tasmota Web Installer](/IMG/TASMOTA-WEB.gif)

## Tasmota integration and configuration into Home Assistant:

Installing this additive is quite easy and does not differ in comparison with the installation of any other Home Assistant supplement.

- Click the Home Assistant My button below to open the add-on to your Home assistant copy.
    
[![To the supplement](https://raw.githubusercontent.com/Bacard1/icon-set-project/9e7e05e78747dc0ecaa404a33cbe9e5d264ad003/button/button%20ADD-ON%20ON.svg)](https://my.home-assistant.io/redirect/supervisor_addon/?addon=a0d7b954_sonweb&repository_url=https%3A%2F%2Fgithub.com%2Fhassio-addons%2Frepository)

- Open this add -on in your Home Assistant copy.

- Click the Installation button to install the additive.

- Start the "Tasmoadmin" supplement.

- Check the log files on the "Tasmoadmin" add -on to see if everything has passed well

- By default, the username is "Admin" and the password "Password".

![TasmoAdmin](/IMG/TASMOTA.gif)

Integration is also easy.Stretch on Bitonut below:

![ADDONS](/IMG/TASMOTA-Finish.gif)

[![To the integration](https://raw.githubusercontent.com/Bacard1/icon-set-project/9e7e05e78747dc0ecaa404a33cbe9e5d264ad003/button/button%20ADD%20INTEGRATION%20TO.svg)](https://my.home-assistant.io/redirect/config_flow_start?domain=tasmota)

> [!NOTE]
> This integration will fully connect Home Assistant to all devices added to the Tasmota additive.Restart Home Assistant and enjoy control of your device.

> [!TIP]
> If you like this project, [ТУК](https://github.com/Bacard1?tab=repositories) You will find more interesting borders made by me. <br>
> If you have difficulty or have questions, do not hesitate to contact me.

[sonoff]: https://www.amazon.de/SONOFF-BASICR4-Lichtschalter-Intelligenter-%C3%9Cberhitzungsschutzfunktion/dp/B0CG8XDJ35/ref=sr_1_2_sspa?__mk_de_DE=%C3%85M%C3%85%C5%BD%C3%95%C3%91&crid=3CMT8DHMKLZV2&dib=eyJ2IjoiMSJ9.KXz9r3CypIhIVQgNxT_fRRIXSv-_QJ7HYot3T9WVhWio4PEeNr_0ODHa9fsuvzBoQtgE-qLeoSI6hQ32-rg9B8qog9vHVBaMA5rrgNjJD1c3010AmXTH5u2_McLbmJKW.UyaG9DIU92qqhsySG8ho9AABr_ownM1IAcmqx6VV7UA&dib_tag=se&keywords=sonoff%2Bbasic&qid=1731277654&s=ce-de&sprefix=sonoff%2Bbasic%2Celectronics%2C90&sr=1-2-spons&sp_csd=d2lkZ2V0TmFtZT1zcF9hdGY&th=1

[azd]: https://www.amazon.de/AZDelivery-Adapter-kompatibel-FT232RL-inklusive/dp/B0DJ2J8LJM/ref=sr_1_1_sspa?__mk_de_DE=%C3%85M%C3%85%C5%BD%C3%95%C3%91&crid=6IF4MKNS4A5T&dib=eyJ2IjoiMSJ9._d-RneqdaNTqbSZPIzlD09nusj5HRIQO-OdnwFACIJPChaFh0mSw_okV_YNRHpHk5hL9HFiuG1JWvmmTtW_lFXNdrgu2gEqH9a1Jys2oqrlRKBEGIV3B6YD85U2tEd1YrLK5gGRQL9O3G8yIEfzxRhauCQTjDdWMGRJJwUEmo7fnqblcY63CtKW0IM2ThWU1Ngu_NxnQpYbzU6GI0_PfVIsR4dZZ3LY2ATQ6J_GWyX_CVp4fCv2gV3zdygqymyBhzKkI92fOa1UI81vrCmBVtrT-OZQdtuI-DC-HPV2Mo1Q.wArW0v1fUUeFpffPXDInIyLM66yaBRHGi-TwZQ-ePS8&dib_tag=se&keywords=TTL%2BSerial%2BConverter%2BAdapter%2Baz&qid=1731285082&s=ce-de&sprefix=ttl%2Bserial%2Bconverter%2Badapter%2Baz%2Celectronics%2C112&sr=1-1-spons&sp_csd=d2lkZ2V0TmFtZT1zcF9hdGY&th=1
