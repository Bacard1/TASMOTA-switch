![BANNER](/IMG/banner.png)

# 🤖 СТАР "SONOFF" С НОВА TASMOTA + HASS ИНТЕГРАЦИЯ

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg?color=ff00d8)](https://opensource.org/licenses/MIT)
![GitHub last commit](https://img.shields.io/github/last-commit/Bacard1/TASMOTA-switch.svg?color=ff00d8)
[![hacs_badge](https://img.shields.io/badge/HACS-2025.5.3-orange.svg?color=ff00d8)](https://github.com/hacs/integration)

[![Home Assistant](https://img.shields.io/badge/.-HOME_ASSISTANT-blue?logo=homeassistant)](https://www.home-assistant.io/) 
[![Donate via PayPal](https://img.shields.io/badge/PayPal-DONATE-blue?logo=paypal)](https://www.paypal.com/donate/?hosted_button_id=AAWFZVF2XCP5A)
![Script](https://img.shields.io/badge/Script-YAML-blue?logo=yaml)

[![Български](https://img.shields.io/badge/BG-ЕЗИК-gree?logo=translate&labelColor=gray&style=flat-square&link=https://example.com/bg
)](BG.md)
[![Deutch](https://img.shields.io/badge/DE-SPRACHE-gree?logo=translate&labelColor=gray&style=flat-square&link=https://example.com/bg
)](DE.md)
[![English](https://img.shields.io/badge/EN-LANGUAGE-gree?logo=translate&labelColor=gray&style=flat-square&link=https://example.com/bg)](README.md)

Това хранилище предлага напълно готова и лесна за използване конфигурация за интегриране на смарт ключове с TASMOTA към Home Assistant. Включени са примери за автоматизации, настройки на MQTT и YAML шаблони, които улесняват управлението на смарт устройствата ви.

Целта на проекта е да предостави енергийно ефективна, лесна за конфигуриране и надеждна автоматизация за ежедневни ситуации в умния дом.

📌 Основни функции:

YAML скриптове за управление на ключове

Автоматизации при промяна на състоянието

Настройка на MQTT интеграция

Примери с енергомониторинг

Поддръжка на български и английски език

## 📦 Съдържание

- [🤖 СТАР "SONOFF" С НОВА TASMOTA + HASS ИНТЕГРАЦИЯ](#-стар-sonoff-с-нова-tasmota--hass-интеграция)
  - [📦 Съдържание](#-съдържание)
    - [🕷️ TASMOTA (софтуер):](#️-tasmota-софтуер)
    - [⚙️ Sonoff BasicR2:](#️-sonoff-basicr2)
    - [🔗 AZDelivery TTL Serial Adapter](#-azdelivery-ttl-serial-adapter)
    - [💾 Драйвери:](#-драйвери)
    - [🧩 Инсталиране:](#-инсталиране)
  - [💊 Flashing Tool:](#-flashing-tool)
  - [💉 Firmware:](#-firmware)
  - [Интеграция и конфигурация на TASMOTA в Home Assistant:](#интеграция-и-конфигурация-на-tasmota-в-home-assistant)

---

### 🕷️ TASMOTA (софтуер):

Флашването на "SONOFF" устройства е решение за пълен котрол над него в локален режим, а възможността те да бъдат интегриран в Home Assistant се грижи за това да не ви липсва облачният режим с който се продават SONOFF.

### ⚙️ [Sonoff BasicR2][sonoff]: 

| ![Sonoff BasicR2](/IMG/BASICR2.png) | Това е устройството което ще флашна със "TASMOTA", а причините са: <br> - *Преминаването на устройството от Офлайн до онляйн му отнема много време* <br> - *Угромен латенц при превключване* <br> - *Често налага конфигурирането на устройството на ново*|
|-----|-----|

> [!CAUTION]
> Преди да продължите изключете ["Sonoff BasicR2"][sonoff] от електрическата мрежа!!!

<br>

### 🔗 [AZDelivery TTL Serial Adapter][azd]

| ![AZDelivery TTL Serial Adapter](/IMG/TTL%20Adapter.png) | AZDelivery TTL Serial Adapter е инструментът с който ще послъжи за свързването, разчитането и флашването на  "Sonoff BasicR" |
|-----|-----|

### 💾 Драйвери:

Преди свързването, е неоходимо да инсталирате драйварите ["CP2102 drivers:"](https://www.silabs.com/products/development-tools/software/usb-to-uart-bridge-vcp-drivers) ["CH342, CH343, CH9102 drivers:"](https://www.wch.cn/downloads/CH343SER_ZIP.html) и ["CH340, CH341 drivers:"](https://www.wch.cn/downloads/CH341SER_ZIP.html). След инсталирането им е необходимо да рестартирате операционната система преди да продължите.

### 🧩 Инсталиране:

> [!CAUTION]
> Преди да продължите се уверете че устойството ["Sonoff BasicR2"][sonoff]  е изключено от електрическата мрежа!!! 
>

> [!NOTE]
> За да свързването на ["Sonoff BasicR2"][sonoff] с ["AZDelivery TTL Serial Adapter"][azd], ще трябва да стигнете до платката на ["Sonoff BasicR2"][sonoff], това означава че се налага да го разглобите!
>
> Погледни схематата на свързване в изображението по долу!!!

<p align=center> 🆒СХЕМА НА СВЪРЗВАНЕ </p>

![Схема на свързване](/IMG/sonoff-basicr2-modul.png)

> [!WARNING]
> Обърнете внимание че RX <--> TX се разменят. Ако се придържате към схемата, то няма да имате проблеми с комуникацията с ["Sonoff BasicR2"][sonoff].


## 💊 Flashing Tool:

- [Tasmota Web Installer](https://tasmota.github.io/install/) - Flash Tasmota, използвайки браузър на базата на хром за ESP82xx и ESP32
- [Tasmotizer](https://github.com/tasmota/tasmotizer/releases) - Инструмент за мигане и изтегляне на фърмуера само за ESP82xx.(Windows, Linux или Mac)
- [ESP-Flasher](https://github.com/Jason2866/ESP_Flasher) - GUI Flasher за Tasmota въз основа на ESPTOOL.py за ESP82XX и ESP32.(Windows, Linux или Mac)
- [Esptool.py](https://github.com/espressif/esptool) - Официалният мигащ инструмент от Espressif за ESP82xx и ESP32.

## 💉 Firmware: 

Изтеглете най новата версия на файлът с име ["tasmota.bin"](https://ota.tasmota.com/tasmota/release/)

За този проект използвах [Tasmota Web Installer](https://tasmota.github.io/install/), с него не се налага да се тегли Firmware. Тои разполага с гама от Firmware от който да избирате.:

![demo Tasmota Web Installer](/IMG/TASMOTA-WEB.gif)

## Интеграция и конфигурация на TASMOTA в Home Assistant:

Инсталирането на тази добавка е доста лесно и не се различава по сравнение с инсталирането на всяка друга добавка Home Assistant.

- Щракнете върху бутона Home Assistant My по-долу, за да отворите добавката на вашия Home Помощник екземпляр.
    
[![КЪМ ДОБАВКАТА](https://raw.githubusercontent.com/Bacard1/icon-set-project/9e7e05e78747dc0ecaa404a33cbe9e5d264ad003/button/button%20ADD-ON%20ON.svg)](https://my.home-assistant.io/redirect/supervisor_addon/?addon=a0d7b954_sonweb&repository_url=https%3A%2F%2Fgithub.com%2Fhassio-addons%2Frepository)

- Отворете тази добавка във вашия екземпляр на Home Assistant.

- Щракнете върху бутона "Инсталиране", за да инсталирате добавката.

- Стартирайте добавката "TasmoAdmin".

- Проверете регистрационните файлове на добавката "TasmoAdmin", за да видите дали всичко е минало добре

- По подразбиране потребителското име е "admin", а паролата "password".  

![TasmoAdmin](/IMG/TASMOTA.gif)

Интеграцията е също така лесна. Щтракнете върху битонут по долу:

![ADDONS](/IMG/TASMOTA-Finish.gif)

[![КЪМ ИНТЕГРАЦИЯТА](https://raw.githubusercontent.com/Bacard1/icon-set-project/9e7e05e78747dc0ecaa404a33cbe9e5d264ad003/button/button%20ADD%20INTEGRATION%20TO.svg)](https://my.home-assistant.io/redirect/config_flow_start?domain=tasmota)

> [!NOTE]
> Тази интеграция ще свърже изцяло, Home Assistant със всички устройства добавени в Добавката TASMOTA . Рестартирайте Home Assistant и се радвайте на контролът върху устройтвата си.

> [!TIP]
> Ако този проект ви е харесъл, [ТУК](https://github.com/Bacard1?tab=repositories) ще намерите още интересни гранилища направени от мен.<br>
> Ако срещате затруднения или имате въпроси не се колебайте да се свържете с мен.

[sonoff]: https://www.amazon.de/SONOFF-BASICR4-Lichtschalter-Intelligenter-%C3%9Cberhitzungsschutzfunktion/dp/B0CG8XDJ35/ref=sr_1_2_sspa?__mk_de_DE=%C3%85M%C3%85%C5%BD%C3%95%C3%91&crid=3CMT8DHMKLZV2&dib=eyJ2IjoiMSJ9.KXz9r3CypIhIVQgNxT_fRRIXSv-_QJ7HYot3T9WVhWio4PEeNr_0ODHa9fsuvzBoQtgE-qLeoSI6hQ32-rg9B8qog9vHVBaMA5rrgNjJD1c3010AmXTH5u2_McLbmJKW.UyaG9DIU92qqhsySG8ho9AABr_ownM1IAcmqx6VV7UA&dib_tag=se&keywords=sonoff%2Bbasic&qid=1731277654&s=ce-de&sprefix=sonoff%2Bbasic%2Celectronics%2C90&sr=1-2-spons&sp_csd=d2lkZ2V0TmFtZT1zcF9hdGY&th=1

[azd]: https://www.amazon.de/AZDelivery-Adapter-kompatibel-FT232RL-inklusive/dp/B0DJ2J8LJM/ref=sr_1_1_sspa?__mk_de_DE=%C3%85M%C3%85%C5%BD%C3%95%C3%91&crid=6IF4MKNS4A5T&dib=eyJ2IjoiMSJ9._d-RneqdaNTqbSZPIzlD09nusj5HRIQO-OdnwFACIJPChaFh0mSw_okV_YNRHpHk5hL9HFiuG1JWvmmTtW_lFXNdrgu2gEqH9a1Jys2oqrlRKBEGIV3B6YD85U2tEd1YrLK5gGRQL9O3G8yIEfzxRhauCQTjDdWMGRJJwUEmo7fnqblcY63CtKW0IM2ThWU1Ngu_NxnQpYbzU6GI0_PfVIsR4dZZ3LY2ATQ6J_GWyX_CVp4fCv2gV3zdygqymyBhzKkI92fOa1UI81vrCmBVtrT-OZQdtuI-DC-HPV2Mo1Q.wArW0v1fUUeFpffPXDInIyLM66yaBRHGi-TwZQ-ePS8&dib_tag=se&keywords=TTL%2BSerial%2BConverter%2BAdapter%2Baz&qid=1731285082&s=ce-de&sprefix=ttl%2Bserial%2Bconverter%2Badapter%2Baz%2Celectronics%2C112&sr=1-1-spons&sp_csd=d2lkZ2V0TmFtZT1zcF9hdGY&th=1
