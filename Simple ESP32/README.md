# Simple ESP32

This is the most simple ESP32 board I could imagine.
It's as small as possible, though able to run [ESP32-Marauder](https://github.com/justcallmekoko/ESP32Marauder) by [justcallmekoko](https://github.com/justcallmekoko).

Please take note that, although I tested everything posible (without the PCB), I could not test the PCB itself.
Nor ist the setup of the Bootstrapping-Pins tested.


## You will have to compile [ESP32-Marauder](https://github.com/justcallmekoko/ESP32Marauder) by yourself, since I changed some of the Pins due to an incompatibility.
The original code uses Pin 6 for one of the LED colors.
Since Pin 6 is used for the SPI-Flash on the ESP-WROOVER-32D I had to change that.
The Pins used for the RGB-LED are now 25, 26 and 27.

To download and compile the Source please follow the original [Instructions](https://github.com/justcallmekoko/ESP32Marauder/wiki/installing-firmware-from-source).
You will have to change the following three lines in `flipperLED.h`:
```
#define B_PIN 4
#define G_PIN 5
#define R_PIN 6
```
to
```
#define B_PIN 27
#define G_PIN 26
#define R_PIN 25
```

To upload to the board you have to do the following Steps:
- Plug the board into the Flipper
- Plug the Flippers USB cable into your computer
- On the Flipper:
	- Go to GPIO in the main menu
	- Select `USB-UART Bridge`
	- Klick the left button to open the `Config` page
	- Make sure the Baudrate is set to `Host`
- Select the Flippers COM Port in your IDE
- Press and hold the `Boot` button on the boad. While holding, press and release the `RST` button. Keep holding `Boot` for 3 more seconds
- Start the upload on your computer

You should now be able to use the ESP32-Marauder with the application on the Flipper.
When using the Flipper as `USB-UART Bridge` you can also interact with the original CLI from the ESP32-Marauder.

## The parts you will need:
- 1x [Header](https://github.com/DereIBims/FlipperExtensions/edit/main/Simple%20ESP32/BOM.md#header)
- 1x [RGB-LED](https://github.com/DereIBims/FlipperExtensions/edit/main/Simple%20ESP32/BOM.md#rgb-led)
- 2x [10k Resistor](https://github.com/DereIBims/FlipperExtensions/edit/main/Simple%20ESP32/BOM.md#resistor) for R1 and R2
- 1x [47Ohm Resistor](https://github.com/DereIBims/FlipperExtensions/edit/main/Simple%20ESP32/BOM.md#resistor-1) for R3
- 2x [Button](https://github.com/DereIBims/FlipperExtensions/edit/main/Simple%20ESP32/BOM.md#buttons)
- 1x [ESP-WROOVER-32D](https://github.com/DereIBims/FlipperExtensions/edit/main/Simple%20ESP32/BOM.md#esp-wroover-32d) or PIN-compatible other ESP32
