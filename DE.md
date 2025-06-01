![BANNER](/IMG/banner.png)  

# 🤖 START "SONOFF" MIT NEUER TASMOTA + HASS INTEGRATION  

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
Dieses Repository bietet eine vollständig vorbereitete und einfach zu verwendende Konfiguration zur Integration von Smart-Schaltern mit TASMOTA in Home Assistant. Enthalten sind Beispiele für Automatisierungen, MQTT-Einstellungen und YAML-Vorlagen, die die Verwaltung Ihrer Smart-Geräte erleichtern.  

Ziel des Projekts ist es, eine energieeffiziente, einfach zu konfigurierende und zuverlässige Automatisierung für alltägliche Situationen im Smart Home bereitzustellen.  

📌 Hauptfunktionen:  

- YAML-Skripte zur Schaltersteuerung  
- Automatisierungen bei Zustandsänderungen  
- MQTT-Integrationskonfiguration  
- Beispiele mit Energieüberwachung  
- Unterstützung für Deutsch und Englisch  

## 📦 Inhalt  

- [🤖 START "SONOFF" MIT NEUER TASMOTA + HASS INTEGRATION](#-start-sonoff-mit-neuer-tasmota--hass-integration)
	- [📦 Inhalt](#-inhalt)
		- [🕷️ TASMOTA (Software):](#️-tasmota-software)
		- [⚙️ Sonoff BasicR2:](#️-sonoff-basicr2)
		- [🔗 AZDelivery TTL Serial Adapter](#-azdelivery-ttl-serial-adapter)
		- [💾 Treiber:](#-treiber)
		- [🧩 Installation:](#-installation)
	- [💊 Flashing-Tool:](#-flashing-tool)
	- [💉 Firmware:](#-firmware)
	- [Integration und Konfiguration von TASMOTA in Home Assistant:](#integration-und-konfiguration-von-tasmota-in-home-assistant)

---  

### 🕷️ TASMOTA (Software):  

Das Flashen von "SONOFF"-Geräten ist eine Lösung für die vollständige lokale Kontrolle darüber, und die Möglichkeit, sie in Home Assistant zu integrieren, sorgt dafür, dass Ihnen die Cloud-Funktionalität, mit der SONOFF verkauft wird, nicht fehlt.  

### ⚙️ [Sonoff BasicR2][sonoff]:  

| ![Sonoff BasicR2](/IMG/BASICR2.png) | Dies ist das Gerät, das mit "TASMOTA" geflasht wird. Die Gründe dafür sind: <br> - *Der Übergang des Geräts vom Offline- zum Online-Modus dauert sehr lange* <br> - *Hohe Latenz beim Schalten* <br> - *Häufige Neukonfiguration des Geräts erforderlich* |  
|-----|-----|  

> [!WARNUNG]  
> Schalten Sie das ["Sonoff BasicR2"][sonoff] vor dem Fortfahren aus dem Stromnetz aus!!!  

<br>  

### 🔗 [AZDelivery TTL Serial Adapter][azd]  

| ![AZDelivery TTL Serial Adapter](/IMG/TTL%20Adapter.png) | Der AZDelivery TTL Serial Adapter ist das Werkzeug, das zum Verbinden, Auslesen und Flashen des "Sonoff BasicR" verwendet wird. |  
|-----|-----|  

### 💾 Treiber:  

Vor dem Verbinden müssen Sie die Treiber ["CP2102-Treiber:"](https://www.silabs.com/products/development-tools/software/usb-to-uart-bridge-vcp-drivers), ["CH342, CH343, CH9102-Treiber:"](https://www.wch.cn/downloads/CH343SER_ZIP.html) und ["CH340, CH341-Treiber:"](https://www.wch.cn/downloads/CH341SER_ZIP.html) installieren. Nach der Installation müssen Sie das Betriebssystem neu starten, bevor Sie fortfahren.  

### 🧩 Installation:  

> [!WARNUNG]  
> Stellen Sie sicher, dass das Gerät ["Sonoff BasicR2"][sonoff] vor dem Fortfahren aus dem Stromnetz ausgeschaltet ist!!!  

> [!HINWEIS]  
> Um das ["Sonoff BasicR2"][sonoff] mit dem ["AZDelivery TTL Serial Adapter"][azd] zu verbinden, müssen Sie die Platine des ["Sonoff BasicR2"][sonoff] freilegen, was bedeutet, dass Sie es zerlegen müssen!  
>  
> Siehe die Verbindungsdiagramm im Bild unten!!!  

<p align=center> 🆒 VERBINDUNGSDIAGRAMM </p>  

![Verbindungsdiagramm](/IMG/sonoff-basicr2-modul.png)  

> [!WARNUNG]  
> Beachten Sie, dass RX <--> TX vertauscht werden. Wenn Sie dem Diagramm folgen, sollten Sie keine Kommunikationsprobleme mit dem ["Sonoff BasicR2"][sonoff] haben.  

## 💊 Flashing-Tool:  

- [Tasmota Web Installer](https://tasmota.github.io/install/) - Tasmota flashen mit einem Chrome-basierten Browser für ESP82xx und ESP32  
- [Tasmotizer](https://github.com/tasmota/tasmotizer/releases) - Flashing-Tool und Firmware-Download nur für ESP82xx (Windows, Linux oder Mac)  
- [ESP-Flasher](https://github.com/Jason2866/ESP_Flasher) - GUI-Flasher für Tasmota basierend auf ESPTOOL.py für ESP82XX und ESP32 (Windows, Linux oder Mac)  
- [Esptool.py](https://github.com/espressif/esptool) - Das offizielle Flashing-Tool von Espressif für ESP82xx und ESP32.  

## 💉 Firmware:  

Laden Sie die neueste Version der Datei mit dem Namen ["tasmota.bin"](https://ota.tasmota.com/tasmota/release/) herunter.  

Für dieses Projekt wurde der [Tasmota Web Installer](https://tasmota.github.io/install/) verwendet, mit dem keine Firmware heruntergeladen werden muss. Es bietet eine Auswahl an Firmware zur Auswahl:  

![Demo Tasmota Web Installer](/IMG/TASMOTA-WEB.gif)  

## Integration und Konfiguration von TASMOTA in Home Assistant:  

Die Installation dieser Erweiterung ist sehr einfach und unterscheidet sich nicht von der Installation einer anderen Home-Assistant-Erweiterung.  

- Klicken Sie auf die Schaltfläche Home Assistant My unten, um die Erweiterung in Ihrer Home-Assistant-Instanz zu öffnen.  

[![ZUR ERWEITERUNG](https://raw.githubusercontent.com/Bacard1/icon-set-project/9e7e05e78747dc0ecaa404a33cbe9e5d264ad003/button/button%20ADD-ON%20ON.svg)](https://my.home-assistant.io/redirect/supervisor_addon/?addon=a0d7b954_sonweb&repository_url=https%3A%2F%2Fgithub.com%2Fhassio-addons%2Frepository)  

- Öffnen Sie diese Erweiterung in Ihrer Home-Assistant-Instanz.  

- Klicken Sie auf die Schaltfläche "Installieren", um die Erweiterung zu installieren.  

- Starten Sie die Erweiterung "TasmoAdmin".  

- Überprüfen Sie die Protokolle der Erweiterung "TasmoAdmin", um sicherzustellen, dass alles korrekt verlaufen ist.  

- Standardmäßig ist der Benutzername "admin" und das Passwort "password".  

![TasmoAdmin](/IMG/TASMOTA.gif)  

Die Integration ist ebenfalls einfach. Klicken Sie auf die Schaltfläche unten:  

![ERWEITERUNGEN](/IMG/TASMOTA-Finish.gif)  

[![ZUR INTEGRATION](https://raw.githubusercontent.com/Bacard1/icon-set-project/9e7e05e78747dc0ecaa404a33cbe9e5d264ad003/button/button%20ADD%20INTEGRATION%20TO.svg)](https://my.home-assistant.io/redirect/config_flow_start?domain=tasmota)  

> [!HINWEIS]  
> Diese Integration verbindet Home Assistant vollständig mit allen Geräten, die der TASMOTA-Erweiterung hinzugefügt wurden. Starten Sie Home Assistant neu und genießen Sie die Kontrolle über Ihre Geräte.  

> [!TIP]  
> Wenn Ihnen dieses Projekt gefallen hat, finden Sie [HIER](https://github.com/Bacard1?tab=repositories) weitere interessante Repositories von mir.  
> Wenn Sie Schwierigkeiten haben oder Fragen haben, zögern Sie nicht, mich zu kontaktieren.  

[sonoff]: https://www.amazon.de/SONOFF-BASICR4-Lichtschalter-Intelligenter-%C3%9Cberhitzungsschutzfunktion/dp/B0CG8XDJ35/ref=sr_1_2_sspa?__mk_de_DE=%C3%85M%C3%85%C5%BD%C3%95%C3%91&crid=3CMT8DHMKLZV2&dib=eyJ2IjoiMSJ9.KXz9r3CypIhIVQgNxT_fRRIXSv-_QJ7HYot3T9WVhWio4PEeNr_0ODHa9fsuvzBoQtgE-qLeoSI6hQ32-rg9B8qog9vHVBaMA5rrgNjJD1c3010AmXTH5u2_McLbmJKW.UyaG9DIU92qqhsySG8ho9AABr_ownM1IAcmqx6VV7UA&dib_tag=se&keywords=sonoff%2Bbasic&qid=1731277654&s=ce-de&sprefix=sonoff%2Bbasic%2Celectronics%2C90&sr=1-2-spons&sp_csd=d2lkZ2V0TmFtZT1zcF9hdGY&th=1  

[azd]: https://www.amazon.de/AZDelivery-Adapter-kompatibel-FT232RL-inklusive/dp/B0DJ2J8LJM/ref=sr_1_1_sspa?__mk_de_DE=%C3%85M%C3%85%C5%BD%C3%95%C3%91&crid=6IF4MKNS4A5T&dib=eyJ2IjoiMSJ9._d-RneqdaNTqbSZPIzlD09nusj5HRIQO-OdnwFACIJPChaFh0mSw_okV_YNRHpHk5hL9HFiuG1JWvmmTtW_lFXNdrgu2gEqH9a1Jys2oqrlRKBEGIV3B6YD85U2tEd1YrLK5gGRQL9O3G8yIEfzxRhauCQTjDdWMGRJJwUEmo7fnqblcY63CtKW0IM2ThWU1Ngu_NxnQpYbzU6GI0_PfVIsR4dZZ3LY2ATQ6J_GWyX_CVp4fCv2gV3zdygqymyBhzKkI92fOa1UI81vrCmBVtrT-OZQdtuI-DC-HPV2Mo1Q.wArW0v1fUUeFpffPXDInIyLM66yaBRHGi-TwZQ-ePS8&dib_tag=se&keywords=TTL%2BSerial%2BConverter%2BAdapter%2Baz&qid=1731285082&s=ce-de&sprefix=ttl%2Bserial%2Bconverter%2Badapter%2Baz%2Celectronics%2C112&sr=1-1-spons&sp_csd=d2lkZ2V0Tm