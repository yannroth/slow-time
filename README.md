# SlowTime

A smartwatch that is more an activity tracker for outdoor people than actually smart. Most available products are completely bloated with features that makes them hard to use. The main goal is to provide a product that doesn't add any hassle to the user. Also, most watches on the market don't focus enough on battery life which is a primary concern for this SlowTime. This tracker displays information on a minute base and not seconds. NO ONE actually needs second accuracy when taking the time to enjoy wilderness.

The journey is the reward.

## Features
- GPS Tracking
- Precise altitude tracking
- Compass
- BLE communication with phone for configuration upload and data download
- Long battery life when tracking
- Extra long battery life when not tracking
- Shows activity information, not notifications
- Human interface implemented with physical buttons and minimal interfaces
- Hackable
- Repearable with easy to source components
- Memory for 1 week of continuous tracking at 1Hz

### Nice to have
- Standard charge connector directly on watch, else open source usb-c adapter
- Heart rate monitor
- Light on display

## Components selection

### MCU
For the choice of MCU, it mostly depends on GPIO considering other components chosen. Nordic NRF52 series fits well the need with integrated BLE.

| Chip | Size [mm] | Link |
| ---  | --------- | ---- |
| nrf52832CIAAE0 | 3 x 3.2 | [link](https://www.nordicsemi.com/Products/nRF52832) |

### GNSS chip

#### With integrated antenna

| Chip      | Base chip | Size [mm]         | Power supply |Power consumption tracking continuous | Power consumption backup | Link |
| --------- | --------- | ----------------- | --- | -------------------------- | ---------------------- | ---- |
| uBlox SAM-M10Q  | ??? | 15.5 x 15.5 x 6.3 | ??? | 9 + 2.3 mA @ 3 V           | 28 uA @ 3.3 V           | [link](https://www.u-blox.com/en/product/sam-m10q-module) |
| uBlox SAM-M8Q   | ??? | 15.5 x 15.5 x 6.3 | ??? | 29 mA @ 3 V               | 20 uA @ 3 V             | [link](https://www.u-blox.com/en/product/sam-m8q-module) |
| uBlox CAM-M8-Q  | ??? | 14 x 9.6 x 1.95   | ??? | 23 mA @ @ 3 V            | 15 uA @ 3 V             | [link](https://www.u-blox.com/en/product/cam-m8-series) |
| Quectel LC86L   | ??? | 16.0 x 16.0 x 6.95 | ??? | 31 mA @ 3.3 V             | 6 uA @ 3.3 V            | [link](https://www.quectel.com/product/gnss-lc86l-series) |
| Quectel L96     | ??? | 14.0 x 9.6 x 2.5 | ??? | 20 mA @ 3.3 V               | 7 uA @ 3.3 V            | [link](https://www.quectel.com/product/gnss-l96) |
| Adafruit Ultimate GPS | ??? | 16.0 x 16.0 x 5 | ??? | 20 mA @ 3.3 V          | 7 uA @ 3.3 V           | [link](https://www.adafruit.com/product/790) |
| Telit SE868K3-AL | ??? | 11 x 11 x 4.1 | ??? | 30 mA @ 3 V                   | 10 uA @ 3 V            | [link](https://www.telit.com/devices/se868k3-a-al/) |
| Telit SE868K7-A | ??? | 11 x 11 x 6.1 | ??? | 24 mA @ 3 V                    | 10 uA @ 3 V            | [link](https://www.telit.com/devices/se868k7-a-se868k7-al/) |
| Antenova M20050-1 | MTK3333 | 13.8 x 9.5 x 1.8 | 2.8 V - 4.3 V @ ??? mA | 25 mA @ 3.3V | 30 uA @ 3.3 V | [link](https://www.antenova.com/product/gps-radionova-rf-antenna-module/) |
| Antenova M20072 | AG3335MN | 13.8 x 9.5 x 1.8 | 1.62 V - 1.98 V @ ??? mA | 12 mA @ 1.8V | 100 uA @ 1.8 V | [link](https://www.antenova.com/product/gnssnova-m20072/) |


### Antenna

In case choosing a module without integrated antenna but with a u.fl connector

| Antenna   | Size [mm] | Link |
| --------- | --------- | ---- |
| Antenova Robusta | 23 x 16 x 1.6 | [link](https://www.antenova.com/product/1559-1609-mhz-robusta-non-detuning-antenna-metal-surfaces/)
| Antenova Bentoni | 40 x 14 x 0.15 | [link](https://www.antenova.com/product/gnss-bentoni-antenna/)
| Linx ANT-GNFPC-SHL150UF | 25 x 25 x 0.1 | [link](https://www.mouser.ch/ProductDetail/Linx-Technologies/ANT-GNFPC-SHL150UF?qs=IPgv5n7u5Qb5MRxxe50rhQ%3D%3D)
| Taoglas Cloud FXP611 | 38 x 37 x 0.15 | [link](https://www.taoglas.com/product/cloud-fxp611-gps-glonass-compass-flexible-pcb-2/)
| Molex 2065600050 | 40.4 x 15.4 x 2 | [link](https://www.molex.com/en-us/products/part-detail/2065600050)
| Pulse W3908B0100 | 26.8 x 20 x 0.15 | [link](https://www.mouser.ch/ProductDetail/Pulse-Electronics/W3908B0100?qs=pfd5qewlna5qgZ3FEn9H5w%3D%3D)


### Pressure sensor
SlowTime need an accurate reading of pressure for altitude measurement.

| Sensor | Size [mm] | Power consumption [uA at 1Hz] | Link |
| ------ | --------- | ----------------------------- | ---- |
| Bosch BMP581 | 2 x 2 x 0.75 | 1.3 uA | [link](https://www.bosch-sensortec.com/products/environmental-sensors/pressure-sensors/bmp581/) |

### Compass
When the visibility is at its lowest, SlowTime is able to provide accurate direction for the north which can be vital in extrem conditions

| Sensor | Size [mm] | Power consumption [uA] | Link |
| ------ | --------- | ---------------------- | ---- |
| ST IIS2MDC | 2 x 2 x 0.7 | 25 at 10Hz | [link](https://www.st.com/en/mems-and-sensors/iis2mdc.html) |
| Bosch BMM350 | 1.28 x 1.28 x 0.5 | 12 at 1.5625Hz, 23 at 12.5Hz | [link](https://www.bosch-sensortec.com/products/motion-sensors/magnetometers/bmm350/) |

### Display
The main aspect of user interface is the display. For the SlowTime, refresh rate is not a priority, firmware will be optimized to be as static as possible on the human interface. Time, altitude, distances, elapsed time and other info will be refreshed every minute. A button can be pushed to force to update data (usefull for compass) and a few seconds (<= 2s) is acceptable for refresh time. Hence, using eInk display seem to be a good option especially as it doesn't suck any power between refreshes and allow user to check the time at any time.

| Display | Size [mm] | Resolution [px] | Link |
| ------- | --------- | --------------- | ---- |
| Good Display GDEY0154D67 | 31.8 x 37.32 x 1 | 200 x 200 | [link](https://www.good-display.com/product/388.html) |

## Market study

### PineTime
Open source nRF52832 based smartwatch with heart rate sensor but no GNSS. Only firmware open source and schematics.  
[link](https://www.pine64.org/pinetime/)

### Open SmartWatch
Open source and open hardware, one version with GPS (L96) one without. No heart rate sensor. Based on ESP32-pico-D4 with BLE and WiFi. [link](https://open-smartwatch.github.io/)


### ZSWatch
An open source and open hardware smart watch with firmware in zephyr. Seem as bloated as commercial product which is exactly what is to be avoided with SlowTime but certainly an excellent reference and starting point. [link](https://github.com/jakkra/ZSWatch)

### Garmin Fenix 6X Pro
Disassembly : [link](http://www.f-blog.info/garmin-fenix-6x-pro-disassembly-or-teardown-whatever-you-say/)

### Garmin Fenix 7X Solar
Disassembly : [link](http://www.f-blog.info/garmin-fenix-7x-solar-teardown-non-destructive/)
[link2](https://www.ifixit.com/Teardown/Garmin+f%C4%93nix+7X+Teardown/156672)
