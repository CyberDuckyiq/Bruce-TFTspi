![Bruce Main Menu](./media/pictures/bruce_banner.jpg)

# :shark: Bruce

Bruce is meant to be a versatile ESP32 firmware that supports a ton of offensive features focusing on facilitating Red Team operations.
It also supports m5stack products and works great with Cardputer, Sticks, M5Cores, T-Decks and T-Embeds.

# :duck: Bruce moded features
> **Moded by:** + [@alhelfi](https://github.com/alhelfi) ADD buttons and fix touch.
## ✅ Features

-  Fixed touch for TFT SPI 
    The inverted touch issue on the 2.4 and 2.8 TFT SPI displays has been resolved. Previously, the touch was inverted, meaning that when you pressed the right, you pressed the left, and vice versa.
-  buttons for TFT SPI 
    Run Bruce with buttons on a TFT
    Note: When boot the device on a 2.4 TFT display, the colors are reversed. Go to Settings, then turn on the colors, and cancel Dim Time.

## 📝 Notes

> ⚠️ Don't add all modules together .
> 
>  ⚠️ When boot the device on a 2.4 TFT display with buttons, the colors are reversed. Go to Settings, then turn on the colors, and cancel Dim Time. .


##  install 
flash the BINs files from [release](https://github.com/CyberDuckyiq/Bruce-TFTspi/releases/tag/1.9.1) 
##  ADD modules for bruce with TFT (DIY)

## buttons Connection to ESP32

| Function        | GPIO Pin |
| --------------- | -------- |
| Next Button     | 32       |
| Previous Button | 33       |
| Select Button   | 25       |
| Escape Button   | 26       |

>buttons with esp
>**Note:** The other side of each button should be connected to **GND**.

## TFT SPI 2.4 or 2.8 Connection to ESP32

| Signal       | GPIO Pin       |
|--------------|----------------|
| SDO (MISO)   | GPIO 12        |
| LED          | GPIO 21        |
| SCK          | GPIO 14        |
| SDI (MOSI)   | GPIO 13        |
| D/C          | GPIO 2         |
| RESET        | EN / RESET Pin |
| CS           | GPIO 15        |
| GND          | GND            |
| VCC          | 5V (or 3.3V)*   |

## SD Card Connection to ESP32 

| SD Card Pin | ESP32 GPIO | Description         |
|-------------|------------|---------------------|
| CS          | GPIO5      | Chip Select (CS)    |
| SCK         | GPIO18     | Serial Clock (SCK)  |
| MOSI        | GPIO23     | Master Out Slave In |
| MISO        | GPIO19     | Master In Slave Out |
| VCC         | 3V         | Power Supply        |
| GND         | GND        | Ground              |

> ⚠️ **Note:** The SD card must be formatted as **FAT32** for proper operation.



## Direct Connection Between NRF24L01 and ESP32

| NRF24L01 Pin | ESP32 GPIO | Description             |
|--------------|-------------|--------------------------|
| VCC          | 3.3V        | Power Supply (⚠️ Do NOT use 5V!) |
| GND          | GND         | Ground                   |
| CE           | GPIO22      | Chip Enable              |
| CSN (CNS)    | GPIO27      | SPI Chip Select (CS)     |
| SCK          | GPIO18      | SPI Clock                |
| MOSI         | GPIO23      | SPI MOSI (Master Out)    |
| MISO         | GPIO19      | SPI MISO (Master In)     |
| IRQ          | Not connected or optional | Interrupt (optional) |

> ⚠️ **Note:** NRF24L01 must be powered with **3.3V only**, not 5V.  
> ⚠️ **Important:** You must **remove the SD card** when using the NRF24L01 module to avoid SPI conflicts.



## Direct Connection Between CC1101 v1 and ESP32

| NRF24L01 Pin | ESP32 GPIO                | Description                      |
| ------------ | ------------------------- | -------------------------------- |
| VCC          | 3.3V                      | Power Supply (⚠️ Do NOT use 5V!) |
| GND          | GND                       | Ground                           |
| GDO2         | GPIO22                    | Chip Enable                      |
| CSN (CNS)    | GPIO27                    | SPI Chip Select (CS)             |
| SCK          | GPIO18                    | SPI Clock                        |
| MOSI         | GPIO23                    | SPI MOSI (Master Out)            |
| MISO         | GPIO19                    | SPI MISO (Master In)             |
| IRQ          | Not connected or optional | Interrupt (optional)             |



## PN532 I2C Connection with ESP32 (CYD Board)

| PN532 Pin | ESP32 GPIO | Description            |
|-----------|-------------|-------------------------|
| VCC       | 3.3V        | Power Supply (3.3V only)|
| GND       | GND         | Ground                  |
| SDA       | GPIO27      | I2C Data (SDA)          |
| SCL       | GPIO22      | I2C Clock (SCL)         |

> ⚠️ **Note:** Ensure PN532 is set to **I2C mode** using the onboard switch or jumpers.


## TFT SPI 2.4 or 2.8 Connection to ESP32 for Touch

| Function   | Connected to GPIO |
| ---------- | ----------------- |
| T_IRQ      | VP                |
| T_OUT      | VN                |
| T_DIN      | GPIO 32           |
| T_CS       | GPIO 33           |
| T_CLK      | GPIO 25           |
| SDO (MISO) | GPIO 12           |
| LED        | GPIO 21           |
| SCK        | GPIO 14           |
| SDI (MOSI) | GPIO 13           |
| D/C        | GPIO 2            |
| RESET      | EN / RESET        |
| CS         | GPIO 15           |
| GND        | GND               |
| VCC        | 3.3V              |








## :bookmark_tabs: Wiki

For more information on each function supported by Bruce, [read our wiki here](https://github.com/pr3y/Bruce/wiki).
Also, [read our FAQ](https://github.com/pr3y/Bruce/wiki/FAQ)

## :computer: List of Features

<details>
  <summary><h2>WiFi</h2></summary>

- [x] Connect to WiFi
- [x] WiFi AP
- [x] Disconnect WiFi
- [x] [WiFi Atks](https://github.com/pr3y/Bruce/wiki/WiFi#wifi-atks)
  - [x] [Beacon Spam](https://github.com/pr3y/Bruce/wiki/WiFi#beacon-spam)
  - [x] [Target Atk](https://github.com/pr3y/Bruce/wiki/WiFi#target-atk)
    - [x] Information
    - [x] Target Deauth
    - [x] EvilPortal + Deauth
  - [x] Deauth Flood (More than one target)
- [x] [Wardriving](https://github.com/pr3y/Bruce/wiki/Wardriving)
- [x] [TelNet](https://github.com/pr3y/Bruce/wiki/WiFi#telnet)
- [x] [SSH](https://github.com/pr3y/Bruce/wiki/WiFi#ssh)
- [x] [RAW Sniffer](https://github.com/pr3y/Bruce/wiki/WiFi#raw-sniffer)
- [x] [TCP Client](https://github.com/pr3y/Bruce/wiki/WiFi#tcp-client)
- [x] [TCP Listener](https://github.com/pr3y/Bruce/wiki/WiFi#tcp-listener)
- [x] [DPWO-ESP32](https://github.com/pr3y/Bruce/wiki/WiFi#dpwo-esp32)
- [x] [Evil Portal](https://github.com/pr3y/Bruce/wiki/WiFi#evil-portal)
- [x] [Scan Hosts](https://github.com/pr3y/Bruce/wiki/WiFi#evil-portal)
- [x] [Wireguard Tunneling](https://github.com/pr3y/Bruce/wiki/WiFi#wireguard-tunneling)
- [x] Brucegotchi
  - [x] Pwnagotchi friend
  - [x] Pwngrid spam faces & names
    - [x] [Optional] DoScreen a very long name and face
    - [x] [Optional] Flood uniq peer identifiers

</details>

<details>
  <summary><h2>BLE</h2></summary>

- [X] [BLE Scan](https://github.com/pr3y/Bruce/wiki/BLE#ble-scan)
- [X] Bad BLE - Run Ducky scripts, similar to [BadUsb](https://github.com/pr3y/Bruce/wiki/Others#badusb)
- [X] BLE Keyboard - Cardputer and T-Deck Only
- [X] iOS Spam
- [X] Windows Spam
- [X] Samsung Spam
- [X] Android Spam
- [X] Spam All
</details>


<details>
  <summary><h2>RF</h2></summary>

- [x] Scan/Copy
- [x] [Custom SubGhz](https://github.com/pr3y/Bruce/wiki/RF#replay-payloads-like-flipper)
- [x] Spectrum
- [x] Jammer Full (sends a full squared wave into output)
- [x] Jammer Intermittent (sends PWM signal into output)
- [x] Config
    - [X] RF TX Pin
    - [X] RF RX Pin
    - [X] RF Module
        - [x] RF433 T/R M5Stack
        - [x] [CC1101 (Sub-Ghz)](https://github.com/pr3y/Bruce/wiki/CC1101)
    - [X] RF Frequency
- [x] Replay
</details>

<details>
  <summary><h2>RFID</h2></summary>

- [x] Read tag
- [x] Read 125kHz
- [x] Clone tag
- [x] Write NDEF records
- [x] Amiibolink
- [x] Chameleon
- [x] Write data
- [x] Erase data
- [x] Save file
- [x] Load file
- [x] Config
    - [X] [RFID Module](https://github.com/pr3y/Bruce/wiki/RFID#supported-modules)
        - [x] PN532
        - [x] PN532Killer
- [ ] Emulate tag
</details>

<details>
  <summary><h2>IR</h2></summary>

- [x] TV-B-Gone
- [x] IR Receiver
- [x] [Custom IR (NEC, NECext, SIRC, SIRC15, SIRC20, Samsung32, RC5, RC5X, RC6)](https://github.com/pr3y/Bruce/wiki/IR#replay-payloads-like-flipper)
- [x] Config
    - [X] Ir TX Pin
    - [X] Ir RX Pin
</details>

<details>
  <summary><h2>FM</h2></summary>

- [x] [Broadcast standard](https://github.com/pr3y/Bruce/wiki/FM#play_or_pause_button-broadcast-standard)
- [x] [Broadcast reserved](https://github.com/pr3y/Bruce/wiki/FM#no_entry_sign-broadcast-rerserved)
- [x] [Broadcast stop](https://github.com/pr3y/Bruce/wiki/FM#stop_button-broadcast-stop)
- [ ] [FM Spectrum](https://github.com/pr3y/Bruce/wiki/FM#ocean-fm-spectrum)
- [ ] [Hijack Traffic Announcements](https://github.com/pr3y/Bruce/wiki/FM#car-hijack-ta)
- [ ] [Config](https://github.com/pr3y/Bruce/wiki/FM#bookmark_tabs-config)
</details>

<details>
  <summary><h2>NRF24</h2></summary>

- [X] [NRF24 Jammer](https://github.com/pr3y/Bruce/wiki/BLE#nrf24-jammer)
- [X] 2.4G Spectrum
- [ ] Mousejack
</details>

<details>
  <summary><h2>Scripts</h2></summary>

- [X] [JavaScript Interpreter](https://github.com/pr3y/Bruce/wiki/Interpreter) [Credits to justinknight93](https://github.com/justinknight93/Doolittle)
</details>

<details>
  <summary><h2>Others</h2></summary>

- [X] Mic Spectrum
- [X] QRCodes
    - [x] Custom
    - [x] PIX (Brazil bank transfer system)
- [x] [SD Card Mngr](https://github.com/pr3y/Bruce/wiki/Others#sd-card-mngr)
    - [x] View image (jpg)
    - [x] File Info
    - [x] [Wigle Upload](https://github.com/pr3y/Bruce/wiki/Wardriving#how-to-upload)
    - [x] Play Audio
    - [x] View File
- [x] [LittleFS Mngr](https://github.com/pr3y/Bruce/wiki/Others#littlefs-mngr)
- [x] [WebUI](https://github.com/pr3y/Bruce/wiki/Others#webui)
    - [x] Server Structure
    - [x] Html
    - [x] SDCard Mngr
    - [x] Spiffs Mngr
- [x] Megalodon
- [x] [BADUsb (New features, LittleFS and SDCard)](https://github.com/pr3y/Bruce/wiki/Others#badusb)
- [x] USB Keyboard - Cardputer and T-Deck Only
- [x] [Openhaystack](https://github.com/pr3y/Bruce/wiki/Others#openhaystack)
- [x] [iButton](https://github.com/pr3y/Bruce/wiki/Others#ibutton)
- [x] [LED Control](https://github.com/pr3y/Bruce/wiki/Others#led-control)
</details>

<details>
  <summary><h2>Clock</h2></summary>

- [X] RTC Support
- [X] NTP time adjust
- [X] Manual adjust
</details>

<details>
  <summary><h2>Connect (ESPNOW)</h2></summary>

- [X] Send File
- [X] Receive File
- [X] Send Commands
- [X] Receive Commands
</details>

<details>
  <summary><h2>Config</h2></summary>

- [x] Brightness
- [x] Dim Time
- [x] Orientation
- [X] UI Color
- [x] Boot Sound on/off
- [x] Clock
- [x] Sleep
- [x] Restart
</details>

## :clap: Acknowledgements
+ [@alhelfi](https://github.com/alhelfi) ADD buttons and fix touch.

+ [@bmorcelli](https://github.com/bmorcelli) for new core and a bunch of new features, also porting to many devices!
+ [@IncursioHack](https://github.com/IncursioHack) for adding RF and RFID modules features.
+ [@Luidiblu](https://github.com/Luidiblu) for logo and UI design assistance.
+ [@eadmaster](https://github.com/eadmaster) for adding a lot of features.
+ [@rennancockles](https://github.com/rennancockles) for a lot of RFID code, refactoring and others features.
+ [@7h30th3r0n3](https://github.com/7h30th3r0n3) refactoring and a lot of help with WiFi attacks.
+ [@Tawank](https://github.com/Tawank) refactoring interpreter among many other things
+ [@pablonymous]() new RF functions to read RAW Data
+ [Smoochiee]() for Bruce PCB design.
+ [TH3_KR4K3N]() for Stick cplus extender PCB design.
+ Everyone who contributed in some way to the project, thanks :heart:

## :construction: Disclaimer

Bruce is a tool for cyber offensive and red team operations, distributed under the terms of the Affero General Public License (AGPL). It is intended for legal and authorized security testing purposes only. Use of this software for any malicious or unauthorized activities is strictly prohibited. By downloading, installing, or using Bruce, you agree to comply with all applicable laws and regulations. This software is provided free of charge, and we do not accept payments for copies or modifications. The developers of Bruce assume no liability for any misuse of the software. Use at your own risk.

