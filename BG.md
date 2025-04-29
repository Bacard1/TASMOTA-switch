<h1 align="center"><strong> :robot:TASMOTA - интеграция в Home Assistant и кракване на устройства :robot:</strong></h1>
:robot:
## TASMOTA - Хардуер/Софтуер:

-  **["Sonoff BasicR2"](https://www.amazon.de/SONOFF-BASICR4-Lichtschalter-Intelligenter-%C3%9Cberhitzungsschutzfunktion/dp/B0CG8XDJ35/ref=sr_1_2_sspa?__mk_de_DE=%C3%85M%C3%85%C5%BD%C3%95%C3%91&crid=3CMT8DHMKLZV2&dib=eyJ2IjoiMSJ9.KXz9r3CypIhIVQgNxT_fRRIXSv-_QJ7HYot3T9WVhWio4PEeNr_0ODHa9fsuvzBoQtgE-qLeoSI6hQ32-rg9B8qog9vHVBaMA5rrgNjJD1c3010AmXTH5u2_McLbmJKW.UyaG9DIU92qqhsySG8ho9AABr_ownM1IAcmqx6VV7UA&dib_tag=se&keywords=sonoff%2Bbasic&qid=1731277654&s=ce-de&sprefix=sonoff%2Bbasic%2Celectronics%2C90&sr=1-2-spons&sp_csd=d2lkZ2V0TmFtZT1zcF9hdGY&th=1):** превключвател който работи сравнително бавно в облака в сравнение с Zigbee братята си.

<img align="center" src="IMG\BASICR2.png"  alt="WLED SoundReactiv" width="100%" height="100%">

["Sonoff BasicR2"](https://www.amazon.de/SONOFF-BASICR4-Lichtschalter-Intelligenter-%C3%9Cberhitzungsschutzfunktion/dp/B0CG8XDJ35/ref=sr_1_2_sspa?__mk_de_DE=%C3%85M%C3%85%C5%BD%C3%95%C3%91&crid=3CMT8DHMKLZV2&dib=eyJ2IjoiMSJ9.KXz9r3CypIhIVQgNxT_fRRIXSv-_QJ7HYot3T9WVhWio4PEeNr_0ODHa9fsuvzBoQtgE-qLeoSI6hQ32-rg9B8qog9vHVBaMA5rrgNjJD1c3010AmXTH5u2_McLbmJKW.UyaG9DIU92qqhsySG8ho9AABr_ownM1IAcmqx6VV7UA&dib_tag=se&keywords=sonoff%2Bbasic&qid=1731277654&s=ce-de&sprefix=sonoff%2Bbasic%2Celectronics%2C90&sr=1-2-spons&sp_csd=d2lkZ2V0TmFtZT1zcF9hdGY&th=1) има потенциял да работи на равно със Zigbee устройствата, но локално. Решението да не работи в облък е "TASMOTA".

- **Подготовка:** За да свържете ["Sonoff BasicR2"](https://www.amazon.de/SONOFF-BASICR4-Lichtschalter-Intelligenter-%C3%9Cberhitzungsschutzfunktion/dp/B0CG8XDJ35/ref=sr_1_2_sspa?__mk_de_DE=%C3%85M%C3%85%C5%BD%C3%95%C3%91&crid=3CMT8DHMKLZV2&dib=eyJ2IjoiMSJ9.KXz9r3CypIhIVQgNxT_fRRIXSv-_QJ7HYot3T9WVhWio4PEeNr_0ODHa9fsuvzBoQtgE-qLeoSI6hQ32-rg9B8qog9vHVBaMA5rrgNjJD1c3010AmXTH5u2_McLbmJKW.UyaG9DIU92qqhsySG8ho9AABr_ownM1IAcmqx6VV7UA&dib_tag=se&keywords=sonoff%2Bbasic&qid=1731277654&s=ce-de&sprefix=sonoff%2Bbasic%2Celectronics%2C90&sr=1-2-spons&sp_csd=d2lkZ2V0TmFtZT1zcF9hdGY&th=1) с компютър, ще ви е необходим четец. За този проект използвах ["AZDelivery TTL Serial Adapter"](https://www.amazon.de/AZDelivery-Adapter-kompatibel-FT232RL-inklusive/dp/B0DJ2J8LJM/ref=sr_1_1_sspa?__mk_de_DE=%C3%85M%C3%85%C5%BD%C3%95%C3%91&crid=6IF4MKNS4A5T&dib=eyJ2IjoiMSJ9._d-RneqdaNTqbSZPIzlD09nusj5HRIQO-OdnwFACIJPChaFh0mSw_okV_YNRHpHk5hL9HFiuG1JWvmmTtW_lFXNdrgu2gEqH9a1Jys2oqrlRKBEGIV3B6YD85U2tEd1YrLK5gGRQL9O3G8yIEfzxRhauCQTjDdWMGRJJwUEmo7fnqblcY63CtKW0IM2ThWU1Ngu_NxnQpYbzU6GI0_PfVIsR4dZZ3LY2ATQ6J_GWyX_CVp4fCv2gV3zdygqymyBhzKkI92fOa1UI81vrCmBVtrT-OZQdtuI-DC-HPV2Mo1Q.wArW0v1fUUeFpffPXDInIyLM66yaBRHGi-TwZQ-ePS8&dib_tag=se&keywords=TTL%2BSerial%2BConverter%2BAdapter%2Baz&qid=1731285082&s=ce-de&sprefix=ttl%2Bserial%2Bconverter%2Badapter%2Baz%2Celectronics%2C112&sr=1-1-spons&sp_csd=d2lkZ2V0TmFtZT1zcF9hdGY&th=1)

    <img align="center" src="IMG\TTL Adapter.png"  alt="WLED SoundReactiv" width="100%" height="100%">

    - Преди свързването, е неоходимо да инсталирате драйварите ["CP2102 drivers:"](https://www.silabs.com/products/development-tools/software/usb-to-uart-bridge-vcp-drivers) ["CH342, CH343, CH9102 drivers:"](https://www.wch.cn/downloads/CH343SER_ZIP.html) и ["CH340, CH341 drivers:"](https://www.wch.cn/downloads/CH341SER_ZIP.html). След инсталирането им е необходимо да рестартирате операционната система преди да продължите.

- **Свързване:** за да свързването на ["Sonoff BasicR2"](https://www.amazon.de/SONOFF-BASICR4-Lichtschalter-Intelligenter-%C3%9Cberhitzungsschutzfunktion/dp/B0CG8XDJ35/ref=sr_1_2_sspa?__mk_de_DE=%C3%85M%C3%85%C5%BD%C3%95%C3%91&crid=3CMT8DHMKLZV2&dib=eyJ2IjoiMSJ9.KXz9r3CypIhIVQgNxT_fRRIXSv-_QJ7HYot3T9WVhWio4PEeNr_0ODHa9fsuvzBoQtgE-qLeoSI6hQ32-rg9B8qog9vHVBaMA5rrgNjJD1c3010AmXTH5u2_McLbmJKW.UyaG9DIU92qqhsySG8ho9AABr_ownM1IAcmqx6VV7UA&dib_tag=se&keywords=sonoff%2Bbasic&qid=1731277654&s=ce-de&sprefix=sonoff%2Bbasic%2Celectronics%2C90&sr=1-2-spons&sp_csd=d2lkZ2V0TmFtZT1zcF9hdGY&th=1) с ["AZDelivery TTL Serial Adapter"](https://www.amazon.de/AZDelivery-Adapter-kompatibel-FT232RL-inklusive/dp/B0DJ2J8LJM/ref=sr_1_1_sspa?__mk_de_DE=%C3%85M%C3%85%C5%BD%C3%95%C3%91&crid=6IF4MKNS4A5T&dib=eyJ2IjoiMSJ9._d-RneqdaNTqbSZPIzlD09nusj5HRIQO-OdnwFACIJPChaFh0mSw_okV_YNRHpHk5hL9HFiuG1JWvmmTtW_lFXNdrgu2gEqH9a1Jys2oqrlRKBEGIV3B6YD85U2tEd1YrLK5gGRQL9O3G8yIEfzxRhauCQTjDdWMGRJJwUEmo7fnqblcY63CtKW0IM2ThWU1Ngu_NxnQpYbzU6GI0_PfVIsR4dZZ3LY2ATQ6J_GWyX_CVp4fCv2gV3zdygqymyBhzKkI92fOa1UI81vrCmBVtrT-OZQdtuI-DC-HPV2Mo1Q.wArW0v1fUUeFpffPXDInIyLM66yaBRHGi-TwZQ-ePS8&dib_tag=se&keywords=TTL%2BSerial%2BConverter%2BAdapter%2Baz&qid=1731285082&s=ce-de&sprefix=ttl%2Bserial%2Bconverter%2Badapter%2Baz%2Celectronics%2C112&sr=1-1-spons&sp_csd=d2lkZ2V0TmFtZT1zcF9hdGY&th=1), ще трябва да стигнете до платката на ["Sonoff BasicR2"](https://www.amazon.de/SONOFF-BASICR4-Lichtschalter-Intelligenter-%C3%9Cberhitzungsschutzfunktion/dp/B0CG8XDJ35/ref=sr_1_2_sspa?__mk_de_DE=%C3%85M%C3%85%C5%BD%C3%95%C3%91&crid=3CMT8DHMKLZV2&dib=eyJ2IjoiMSJ9.KXz9r3CypIhIVQgNxT_fRRIXSv-_QJ7HYot3T9WVhWio4PEeNr_0ODHa9fsuvzBoQtgE-qLeoSI6hQ32-rg9B8qog9vHVBaMA5rrgNjJD1c3010AmXTH5u2_McLbmJKW.UyaG9DIU92qqhsySG8ho9AABr_ownM1IAcmqx6VV7UA&dib_tag=se&keywords=sonoff%2Bbasic&qid=1731277654&s=ce-de&sprefix=sonoff%2Bbasic%2Celectronics%2C90&sr=1-2-spons&sp_csd=d2lkZ2V0TmFtZT1zcF9hdGY&th=1), това означава че се налага да го разглобите!

    ### :warning::warning::warning: Преди да започнете със разглобяването изключете ["Sonoff BasicR2"](https://www.amazon.de/SONOFF-BASICR4-Lichtschalter-Intelligenter-%C3%9Cberhitzungsschutzfunktion/dp/B0CG8XDJ35/ref=sr_1_2_sspa?__mk_de_DE=%C3%85M%C3%85%C5%BD%C3%95%C3%91&crid=3CMT8DHMKLZV2&dib=eyJ2IjoiMSJ9.KXz9r3CypIhIVQgNxT_fRRIXSv-_QJ7HYot3T9WVhWio4PEeNr_0ODHa9fsuvzBoQtgE-qLeoSI6hQ32-rg9B8qog9vHVBaMA5rrgNjJD1c3010AmXTH5u2_McLbmJKW.UyaG9DIU92qqhsySG8ho9AABr_ownM1IAcmqx6VV7UA&dib_tag=se&keywords=sonoff%2Bbasic&qid=1731277654&s=ce-de&sprefix=sonoff%2Bbasic%2Celectronics%2C90&sr=1-2-spons&sp_csd=d2lkZ2V0TmFtZT1zcF9hdGY&th=1) от електрическата мрежа. При свързването му със комютир не трябва да е включен в ел. мрежата. ["AZDelivery TTL Serial Adapter"](https://www.amazon.de/AZDelivery-Adapter-kompatibel-FT232RL-inklusive/dp/B0DJ2J8LJM/ref=sr_1_1_sspa?__mk_de_DE=%C3%85M%C3%85%C5%BD%C3%95%C3%91&crid=6IF4MKNS4A5T&dib=eyJ2IjoiMSJ9._d-RneqdaNTqbSZPIzlD09nusj5HRIQO-OdnwFACIJPChaFh0mSw_okV_YNRHpHk5hL9HFiuG1JWvmmTtW_lFXNdrgu2gEqH9a1Jys2oqrlRKBEGIV3B6YD85U2tEd1YrLK5gGRQL9O3G8yIEfzxRhauCQTjDdWMGRJJwUEmo7fnqblcY63CtKW0IM2ThWU1Ngu_NxnQpYbzU6GI0_PfVIsR4dZZ3LY2ATQ6J_GWyX_CVp4fCv2gV3zdygqymyBhzKkI92fOa1UI81vrCmBVtrT-OZQdtuI-DC-HPV2Mo1Q.wArW0v1fUUeFpffPXDInIyLM66yaBRHGi-TwZQ-ePS8&dib_tag=se&keywords=TTL%2BSerial%2BConverter%2BAdapter%2Baz&qid=1731285082&s=ce-de&sprefix=ttl%2Bserial%2Bconverter%2Badapter%2Baz%2Celectronics%2C112&sr=1-1-spons&sp_csd=d2lkZ2V0TmFtZT1zcF9hdGY&th=1), ще се погрижи за захранването му!

    - **Схема на свързване:**

        <img align="center" src="IMG\sonoff-basicr2-modul.png"  alt="WLED SoundReactiv" width="100%" height="100%">

    :warning: Обърнете внимание че RX <--> TX се разменят. Ако се придържате към схемата, то няма да имате проблеми с комуникацията с ["Sonoff BasicR2"](https://www.amazon.de/SONOFF-BASICR4-Lichtschalter-Intelligenter-%C3%9Cberhitzungsschutzfunktion/dp/B0CG8XDJ35/ref=sr_1_2_sspa?__mk_de_DE=%C3%85M%C3%85%C5%BD%C3%95%C3%91&crid=3CMT8DHMKLZV2&dib=eyJ2IjoiMSJ9.KXz9r3CypIhIVQgNxT_fRRIXSv-_QJ7HYot3T9WVhWio4PEeNr_0ODHa9fsuvzBoQtgE-qLeoSI6hQ32-rg9B8qog9vHVBaMA5rrgNjJD1c3010AmXTH5u2_McLbmJKW.UyaG9DIU92qqhsySG8ho9AABr_ownM1IAcmqx6VV7UA&dib_tag=se&keywords=sonoff%2Bbasic&qid=1731277654&s=ce-de&sprefix=sonoff%2Bbasic%2Celectronics%2C90&sr=1-2-spons&sp_csd=d2lkZ2V0TmFtZT1zcF9hdGY&th=1). 

    - **Flashing Tool:**
        - [Tasmota Web Installer](https://tasmota.github.io/install/) - Flash Tasmota, използвайки браузър на базата на хром за ESP82xx и ESP32
        - [Tasmotizer](https://github.com/tasmota/tasmotizer/releases) - Инструмент за мигане и изтегляне на фърмуера само за ESP82xx.(Windows, Linux или Mac)
        - [ESP-Flasher](https://github.com/Jason2866/ESP_Flasher) - GUI Flasher за Tasmota въз основа на ESPTOOL.py за ESP82XX и ESP32.(Windows, Linux или Mac)
        - [Esptool.py](https://github.com/espressif/esptool) - Официалният мигащ инструмент от Espressif за ESP82xx и ESP32.

    - **Firmware:** Изтеглете най новата версия на файлът с име ["tasmota.bin"](https://ota.tasmota.com/tasmota/release/)

    За този проект използвах [Tasmota Web Installer](https://tasmota.github.io/install/), с него не се налага да се тегли Firmware. Тои разполага с гама от Firmware от който да избирате.:

    <img align="center" src="IMG\TASMOTA-WEB.gif"  alt="TASMOTA-WEB" width="60%" height="60%">

## Интеграция и конфигурация на TASMOTA в Home Assistant:

- **Инсталиране:**Инсталирането на тази добавка е доста лесно и не се различава по сравнение с инсталирането на всяка друга добавка Home Assistant.

    - Щракнете върху бутона Home Assistant My по-долу, за да отворите добавката на вашия Home Помощник екземпляр.

        <a href="https://my.home-assistant.io/redirect/supervisor_addon/?addon=a0d7b954_sonweb&repository_url=https%3A%2F%2Fgithub.com%2Fhassio-addons%2Frepository">
        <img align="center" src="https://raw.githubusercontent.com/Bacard1/icon-set-project/9e7e05e78747dc0ecaa404a33cbe9e5d264ad003/button/button%20ADD-ON%20ON.svg" alt="Към проекта" >
        </a>
        

    - Отворете тази добавка във вашия екземпляр на Home Assistant.

    - Щракнете върху бутона "Инсталиране", за да инсталирате добавката.

    - Стартирайте добавката "TasmoAdmin".

    - Проверете регистрационните файлове на добавката "TasmoAdmin", за да видите дали всичко е минало добре

    - По подразбиране потребителското име е "admin", а паролата "password".  

        <img align="center" src="IMG\TASMOTA ADD ON.png"  alt="Към проекта">

- **Инсталиране:** интеграцията е също така лесна. Щтракнете върху битонут по долу:        

    <a href="https://my.home-assistant.io/redirect/config_flow_start?domain=tasmota">
    <img align="center" src="https://raw.githubusercontent.com/Bacard1/icon-set-project/9e7e05e78747dc0ecaa404a33cbe9e5d264ad003/button/button%20ADD%20INTEGRATION%20TO.svg" alt="Към проекта" >
    </a>

    ⚠️ Тази интеграция ще свърже изцяло, Home Assistant със всички устройства добавени в Добавката TASMOTA . Рестартирайте Home Assistant и се радвайте на контролът върху устройтвата си.
