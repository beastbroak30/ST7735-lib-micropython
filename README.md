# ST7735-lib-micropython
Lib for running st7735 display on micropython based mcu
# ST7735 TFT LCD Driver for MicroPython

This repository contains a modified version of GuyCarver's ST7735.py driver for the ST7735 TFT LCD used with MicroPython. Additionally, it includes various sample scripts to demonstrate its use, similar to the graphicstest sketch for Arduino.

## Text Display and Wrapping Options
- A font file is necessary for displaying text. Some font files are available in GuyCarver's repository.
- A text "nowrap" option has been added with the default setting: `nowrap=False`. This allows flexibility when displaying text on the screen.

## Sample Code
### `graphicstest.py`
- This script is a sample code for testing the display with various graphical elements.
- If this script doesn't work correctly, try replacing `initr()` at line 8 with one of the following initialization functions: `initg()`, `initb()`, or `initb2()`.
- You can also change `rgb(True)` to `rgb(False)` if your LCD module shows incorrect colors (swapping red and blue pixels).

### `tftbmp.py`
- This script demonstrates how to display a bitmap image on the TFT LCD.
- Place a bitmap file named `test128x160.bmp` in the MicroPython file system using a file uploading tool such as `ampy`.

### `offscreen-buffer.py`
- This script shows how you can use an offscreen frame buffer, an instance of the `FrameBuffer` class.
- This was tested on a Raspberry Pi Pico. See the pin connections below for setting it up.

## Pin Connections for ESP32
Here is the pin configuration when using an ESP32 DevKitC board with the ST7735 TFT LCD:

- LCD | ESP32-DevKitC
- ---- | ---------------
- VLED | 3V3
- RST  | IO17
- A0   | IO16 (DC)
- SDA  | IO13 (MOSI)
- SCK  | IO14 (CLK)
- VCC  | 3V3
- CS   | IO18
- GND  | GND

## Pin Connections for Raspberry Pi Pico
These are the pin connections for the Raspberry Pi Pico when using the offscreen buffer script:

- LCD | Raspberry Pi Pico
- ---- | ---------------
- VLED | 3V3
- RST  | GP17
- A0   | GP16 (DC)
- SDA  | GP19 (MOSI)
- SCK  | GP18 (CLK)
- VCC  | 3V3
- CS   | GP20
- GND  | GND

## Additional Notes
- If your LCD module shows incorrect colors, try switching the RGB setting as mentioned in the sample code section.
- If you encounter any issues or have questions, please refer to the issues tab on this repository for community help.

## License
This repository is based on the original work of GuyCarver. Please refer to the license file for more information on usage and distribution.
