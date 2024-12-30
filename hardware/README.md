Irrigation hardware information

## Design Decisions

- Version 2 updated the headers from KF128 (2.54 mm) to KF301 (5.00 mm). This was done to make wires easier to install and for safety on the 240VAC headers.
- Version 2 removed the use of all [strapping pins](https://docs.espressif.com/projects/esptool/en/latest/esp32c3/advanced-topics/boot-mode-selection.html) on the ESP32-C3. The strapping pins are GPIO9, GPIO8 and GPIO2. On version 1 GPIO9 was pulling low and entering the serial bootloader. Leaving GPIO9 unconnected will use an internal pull-up resistor.
- The [G3MB-202P](datasheet/g3mb-ssr-datasheet.pdf) solid state relay works by turning on an LED which acts as an optocoupler. The component has a built-in 440R resistor, which means the status LED for each channel can simply be put in series.
- A status light is added which can be controlled by the ESPHome interface. This is added for debugging.

## Bill of Materials

| Component | Quantity | Price ($AUD) as of 30/Dec/2024 | Notes |
| --- | --- | --- | --- |
PCB | 1 | 45 | JLCPCB with express shipping (5 boards minimum)
Myrra 44304 | 1 | 14.19 | Transformer from 240VAC to 24VAC
ESP32-C3 | 1 | 4 | Runs firmware
HLK-PM03 | 1 | 3 | Converts 240VAC to 3V3 up to 3W for ESP32-C3
G3MB-202P | 8 | 1.50 | Solid state relay with 3V3 trigger
Fuse holder 5 x 20 mm (Keystone 4628) | 1 | 1.14 | Any 5 x 20 mm fuse holder will work
0.63A fuse 20 mm | 1 | 1 | A 0.63A fuse is required by the transformer
KF301-5.0-2P | 1 | 2 | 2 port KF301 PCB mount for 240VAC
KF301-5.0-9P | 1 | 2 | 9 port KF301 PCB mount for 24VAC (8 channels and ground)
Through hole LED (red) | 8 | 0.5 | 8 red LEDs for channel status
Through hole LED (green) | 1 | 0.5 | 1 green LED for debug status
10 nF film capacitor 103J63 | 1 | 0.5 | Decoupling/bypass cap
10 uF electrolytic capacitor | 1 | 0.5 | Decoupling/bypass cap
470R through hole | 1 | 1 | Current limiting resistor for debug LED
8 pin header socket 8.5 mm | 2 | 1.10 | Easy mounting of ESP32-C3
8 pin header terminal | 2 | 0.50 | Easy mounting of ESP32-C3