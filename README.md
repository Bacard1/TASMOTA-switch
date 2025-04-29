# 🤖TASMOTA - Integration into Home Assistant and crashing devices

## TASMOTA - Hardware/software:

-  **["Sonoff BasicR2"](https://www.amazon.de/SONOFF-BASICR4-Lichtschalter-Intelligenter-%C3%9Cberhitzungsschutzfunktion/dp/B0CG8XDJ35/ref=sr_1_2_sspa?__mk_de_DE=%C3%85M%C3%85%C5%BD%C3%95%C3%91&crid=3CMT8DHMKLZV2&dib=eyJ2IjoiMSJ9.KXz9r3CypIhIVQgNxT_fRRIXSv-_QJ7HYot3T9WVhWio4PEeNr_0ODHa9fsuvzBoQtgE-qLeoSI6hQ32-rg9B8qog9vHVBaMA5rrgNjJD1c3010AmXTH5u2_McLbmJKW.UyaG9DIU92qqhsySG8ho9AABr_ownM1IAcmqx6VV7UA&dib_tag=se&keywords=sonoff%2Bbasic&qid=1731277654&s=ce-de&sprefix=sonoff%2Bbasic%2Celectronics%2C90&sr=1-2-spons&sp_csd=d2lkZ2V0TmFtZT1zcF9hdGY&th=1):** A switch that works relatively slowly in the cloud compared to the Zigbee brothers.

<img align="center" src="IMG\BASICR2.png"  alt="WLED SoundReactiv" width="100%" height="100%">

["Sonoff BasicR2"](https://www.amazon.de/SONOFF-BASICR4-Lichtschalter-Intelligenter-%C3%9Cberhitzungsschutzfunktion/dp/B0CG8XDJ35/ref=sr_1_2_sspa?__mk_de_DE=%C3%85M%C3%85%C5%BD%C3%95%C3%91&crid=3CMT8DHMKLZV2&dib=eyJ2IjoiMSJ9.KXz9r3CypIhIVQgNxT_fRRIXSv-_QJ7HYot3T9WVhWio4PEeNr_0ODHa9fsuvzBoQtgE-qLeoSI6hQ32-rg9B8qog9vHVBaMA5rrgNjJD1c3010AmXTH5u2_McLbmJKW.UyaG9DIU92qqhsySG8ho9AABr_ownM1IAcmqx6VV7UA&dib_tag=se&keywords=sonoff%2Bbasic&qid=1731277654&s=ce-de&sprefix=sonoff%2Bbasic%2Celectronics%2C90&sr=1-2-spons&sp_csd=d2lkZ2V0TmFtZT1zcF9hdGY&th=1) It has potential to work equally with Zigbee devices, but locally.The decision not to work in a distant is"TASMOTA".

- ** Preparation: ** To connect["Sonoff BasicR2"](https://www.amazon.de/SONOFF-BASICR4-Lichtschalter-Intelligenter-%C3%9Cberhitzungsschutzfunktion/dp/B0CG8XDJ35/ref=sr_1_2_sspa?__mk_de_DE=%C3%85M%C3%85%C5%BD%C3%95%C3%91&crid=3CMT8DHMKLZV2&dib=eyJ2IjoiMSJ9.KXz9r3CypIhIVQgNxT_fRRIXSv-_QJ7HYot3T9WVhWio4PEeNr_0ODHa9fsuvzBoQtgE-qLeoSI6hQ32-rg9B8qog9vHVBaMA5rrgNjJD1c3010AmXTH5u2_McLbmJKW.UyaG9DIU92qqhsySG8ho9AABr_ownM1IAcmqx6VV7UA&dib_tag=se&keywords=sonoff%2Bbasic&qid=1731277654&s=ce-de&sprefix=sonoff%2Bbasic%2Celectronics%2C90&sr=1-2-spons&sp_csd=d2lkZ2V0TmFtZT1zcF9hdGY&th=1) With a computer, you will need a reader.I used for this project ["AZDelivery TTL Serial Adapter"](https://www.amazon.de/AZDelivery-Adapter-kompatibel-FT232RL-inklusive/dp/B0DJ2J8LJM/ref=sr_1_1_sspa?__mk_de_DE=%C3%85M%C3%85%C5%BD%C3%95%C3%91&crid=6IF4MKNS4A5T&dib=eyJ2IjoiMSJ9._d-RneqdaNTqbSZPIzlD09nusj5HRIQO-OdnwFACIJPChaFh0mSw_okV_YNRHpHk5hL9HFiuG1JWvmmTtW_lFXNdrgu2gEqH9a1Jys2oqrlRKBEGIV3B6YD85U2tEd1YrLK5gGRQL9O3G8yIEfzxRhauCQTjDdWMGRJJwUEmo7fnqblcY63CtKW0IM2ThWU1Ngu_NxnQpYbzU6GI0_PfVIsR4dZZ3LY2ATQ6J_GWyX_CVp4fCv2gV3zdygqymyBhzKkI92fOa1UI81vrCmBVtrT-OZQdtuI-DC-HPV2Mo1Q.wArW0v1fUUeFpffPXDInIyLM66yaBRHGi-TwZQ-ePS8&dib_tag=se&keywords=TTL%2BSerial%2BConverter%2BAdapter%2Baz&qid=1731285082&s=ce-de&sprefix=ttl%2Bserial%2Bconverter%2Badapter%2Baz%2Celectronics%2C112&sr=1-1-spons&sp_csd=d2lkZ2V0TmFtZT1zcF9hdGY&th=1)

    <img align="center" src="IMG\TTL Adapter.png"  alt="WLED SoundReactiv" width="100%" height="100%">

    - Before connecting, it is necessary to install drivers ["CP2102 drivers:"](https://www.silabs.com/products/development-tools/software/usb-to-uart-bridge-vcp-drivers) ["CH342, CH343, CH9102 drivers:"](https://www.wch.cn/downloads/CH343SER_ZIP.html) And ["CH340, CH341 drivers:"](https://www.wch.cn/downloads/CH341SER_ZIP.html). After installing them, you need to restart the operating system before continuing.

- ** Connect: ** to connect the ["Sonoff BasicR2"](https://www.amazon.de/SONOFF-BASICR4-Lichtschalter-Intelligenter-%C3%9Cberhitzungsschutzfunktion/dp/B0CG8XDJ35/ref=sr_1_2_sspa?__mk_de_DE=%C3%85M%C3%85%C5%BD%C3%95%C3%91&crid=3CMT8DHMKLZV2&dib=eyJ2IjoiMSJ9.KXz9r3CypIhIVQgNxT_fRRIXSv-_QJ7HYot3T9WVhWio4PEeNr_0ODHa9fsuvzBoQtgE-qLeoSI6hQ32-rg9B8qog9vHVBaMA5rrgNjJD1c3010AmXTH5u2_McLbmJKW.UyaG9DIU92qqhsySG8ho9AABr_ownM1IAcmqx6VV7UA&dib_tag=se&keywords=sonoff%2Bbasic&qid=1731277654&s=ce-de&sprefix=sonoff%2Bbasic%2Celectronics%2C90&sr=1-2-spons&sp_csd=d2lkZ2V0TmFtZT1zcF9hdGY&th=1) with ["AZDelivery TTL Serial Adapter"](https://www.amazon.de/AZDelivery-Adapter-kompatibel-FT232RL-inklusive/dp/B0DJ2J8LJM/ref=sr_1_1_sspa?__mk_de_DE=%C3%85M%C3%85%C5%BD%C3%95%C3%91&crid=6IF4MKNS4A5T&dib=eyJ2IjoiMSJ9._d-RneqdaNTqbSZPIzlD09nusj5HRIQO-OdnwFACIJPChaFh0mSw_okV_YNRHpHk5hL9HFiuG1JWvmmTtW_lFXNdrgu2gEqH9a1Jys2oqrlRKBEGIV3B6YD85U2tEd1YrLK5gGRQL9O3G8yIEfzxRhauCQTjDdWMGRJJwUEmo7fnqblcY63CtKW0IM2ThWU1Ngu_NxnQpYbzU6GI0_PfVIsR4dZZ3LY2ATQ6J_GWyX_CVp4fCv2gV3zdygqymyBhzKkI92fOa1UI81vrCmBVtrT-OZQdtuI-DC-HPV2Mo1Q.wArW0v1fUUeFpffPXDInIyLM66yaBRHGi-TwZQ-ePS8&dib_tag=se&keywords=TTL%2BSerial%2BConverter%2BAdapter%2Baz&qid=1731285082&s=ce-de&sprefix=ttl%2Bserial%2Bconverter%2Badapter%2Baz%2Celectronics%2C112&sr=1-1-spons&sp_csd=d2lkZ2V0TmFtZT1zcF9hdGY&th=1), You will need to get to the board of ["Sonoff BasicR2"](https://www.amazon.de/SONOFF-BASICR4-Lichtschalter-Intelligenter-%C3%9Cberhitzungsschutzfunktion/dp/B0CG8XDJ35/ref=sr_1_2_sspa?__mk_de_DE=%C3%85M%C3%85%C5%BD%C3%95%C3%91&crid=3CMT8DHMKLZV2&dib=eyJ2IjoiMSJ9.KXz9r3CypIhIVQgNxT_fRRIXSv-_QJ7HYot3T9WVhWio4PEeNr_0ODHa9fsuvzBoQtgE-qLeoSI6hQ32-rg9B8qog9vHVBaMA5rrgNjJD1c3010AmXTH5u2_McLbmJKW.UyaG9DIU92qqhsySG8ho9AABr_ownM1IAcmqx6VV7UA&dib_tag=se&keywords=sonoff%2Bbasic&qid=1731277654&s=ce-de&sprefix=sonoff%2Bbasic%2Celectronics%2C90&sr=1-2-spons&sp_csd=d2lkZ2V0TmFtZT1zcF9hdGY&th=1), This means you have to disassemble it!

    ### :warning::warning::warning: Before you start disassembling, turn off ["Sonoff BasicR2"](https://www.amazon.de/SONOFF-BASICR4-Lichtschalter-Intelligenter-%C3%9Cberhitzungsschutzfunktion/dp/B0CG8XDJ35/ref=sr_1_2_sspa?__mk_de_DE=%C3%85M%C3%85%C5%BD%C3%95%C3%91&crid=3CMT8DHMKLZV2&dib=eyJ2IjoiMSJ9.KXz9r3CypIhIVQgNxT_fRRIXSv-_QJ7HYot3T9WVhWio4PEeNr_0ODHa9fsuvzBoQtgE-qLeoSI6hQ32-rg9B8qog9vHVBaMA5rrgNjJD1c3010AmXTH5u2_McLbmJKW.UyaG9DIU92qqhsySG8ho9AABr_ownM1IAcmqx6VV7UA&dib_tag=se&keywords=sonoff%2Bbasic&qid=1731277654&s=ce-de&sprefix=sonoff%2Bbasic%2Celectronics%2C90&sr=1-2-spons&sp_csd=d2lkZ2V0TmFtZT1zcF9hdGY&th=1) from the electrical grid.When connecting it to a Combutr, it must not be included in the mains. ["AZDelivery TTL Serial Adapter"](https://www.amazon.de/AZDelivery-Adapter-kompatibel-FT232RL-inklusive/dp/B0DJ2J8LJM/ref=sr_1_1_sspa?__mk_de_DE=%C3%85M%C3%85%C5%BD%C3%95%C3%91&crid=6IF4MKNS4A5T&dib=eyJ2IjoiMSJ9._d-RneqdaNTqbSZPIzlD09nusj5HRIQO-OdnwFACIJPChaFh0mSw_okV_YNRHpHk5hL9HFiuG1JWvmmTtW_lFXNdrgu2gEqH9a1Jys2oqrlRKBEGIV3B6YD85U2tEd1YrLK5gGRQL9O3G8yIEfzxRhauCQTjDdWMGRJJwUEmo7fnqblcY63CtKW0IM2ThWU1Ngu_NxnQpYbzU6GI0_PfVIsR4dZZ3LY2ATQ6J_GWyX_CVp4fCv2gV3zdygqymyBhzKkI92fOa1UI81vrCmBVtrT-OZQdtuI-DC-HPV2Mo1Q.wArW0v1fUUeFpffPXDInIyLM66yaBRHGi-TwZQ-ePS8&dib_tag=se&keywords=TTL%2BSerial%2BConverter%2BAdapter%2Baz&qid=1731285082&s=ce-de&sprefix=ttl%2Bserial%2Bconverter%2Badapter%2Baz%2Celectronics%2C112&sr=1-1-spons&sp_csd=d2lkZ2V0TmFtZT1zcF9hdGY&th=1), He will take care of his power!

    - ** Connection scheme: **

        <img align="center" src="IMG\sonoff-basicr2-modul.png"  alt="WLED SoundReactiv" width="100%" height="100%">

    :warning: Note that RX <-> TX are exchanged.If you stick to the scheme, then you will have no problems with communication with ["Sonoff BasicR2"](https://www.amazon.de/SONOFF-BASICR4-Lichtschalter-Intelligenter-%C3%9Cberhitzungsschutzfunktion/dp/B0CG8XDJ35/ref=sr_1_2_sspa?__mk_de_DE=%C3%85M%C3%85%C5%BD%C3%95%C3%91&crid=3CMT8DHMKLZV2&dib=eyJ2IjoiMSJ9.KXz9r3CypIhIVQgNxT_fRRIXSv-_QJ7HYot3T9WVhWio4PEeNr_0ODHa9fsuvzBoQtgE-qLeoSI6hQ32-rg9B8qog9vHVBaMA5rrgNjJD1c3010AmXTH5u2_McLbmJKW.UyaG9DIU92qqhsySG8ho9AABr_ownM1IAcmqx6VV7UA&dib_tag=se&keywords=sonoff%2Bbasic&qid=1731277654&s=ce-de&sprefix=sonoff%2Bbasic%2Celectronics%2C90&sr=1-2-spons&sp_csd=d2lkZ2V0TmFtZT1zcF9hdGY&th=1). 

    - **Flashing Tool:**
        - [Tasmota Web Installer](https://tasmota.github.io/install/) - Flash Tasmota using a chrome -based browser for ESP82XX and ESP32
        - [Tasmotizer](https://github.com/tasmota/tasmotizer/releases) - Firmware Flashing and Download only for ESP82XX. (Windows, Linux or Mac)
        - [ESP-Flasher](https://github.com/Jason2866/ESP_Flasher) - Gui Flasher for Tasmota based on ESPTOOL.py for ESP82XX and ESP32. (Windows, Linux or Mac)
        - [Esptool.py](https://github.com/espressif/esptool) - The official flashing tool from ESPRESFIF for ESP82XX and ESP32.

    - **Firmware:** Download the latest version of the file with a name["tasmota.bin"](https://ota.tasmota.com/tasmota/release/)

    I used for this project[Tasmota Web Installer](https://tasmota.github.io/install/), It does not have to draw Firmware.It has a range of Firmware to choose from.:

    <img align="center" src="IMG\TASMOTA-WEB.gif"  alt="TASMOTA-WEB" width="60%" height="60%">

## Integration and configuration of Tasmota into Home Assistant:

  - ** Installation: ** Installing this additive is quite easy and does not differ in comparison with the installation of any other Home Assistant supplement.

  - Click the Home Assistant My button below to open the add-on to your Home assistant copy.

        <a href="https://my.home-assistant.io/redirect/supervisor_addon/?addon=a0d7b954_sonweb&repository_url=https%3A%2F%2Fgithub.com%2Fhassio-addons%2Frepository">
        <img align="center" src="https://raw.githubusercontent.com/Bacard1/icon-set-project/9e7e05e78747dc0ecaa404a33cbe9e5d264ad003/button/button%20ADD-ON%20ON.svg" alt="Към проекта" >
        </a>
        

    - Open this add -on in your Home Assistant copy.

    - Click the Install button to install the additive.

    - Start the "Tasmoadmin" supplement.

    - Check the "tasmoadmin" add -on to see if everything has passed well

    - By default, the username is "Admin" and the password "Password".

        <img align="center" src="IMG\TASMOTA ADD ON.png"  alt="Към проекта">

- ** Installation: ** Integration is also easy.Stretch on Bitonut below:

    <a href="https://my.home-assistant.io/redirect/config_flow_start?domain=tasmota">
    <img align="center" src="https://raw.githubusercontent.com/Bacard1/icon-set-project/9e7e05e78747dc0ecaa404a33cbe9e5d264ad003/button/button%20ADD%20INTEGRATION%20TO.svg" alt="To the project" >
    </a>

   ⚠️ This integration will fully connect Home Assistant to all devices added to the Tasmota supplement.Restart Home Assistant and enjoy control of your device.
