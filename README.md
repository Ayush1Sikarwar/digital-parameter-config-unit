# OLED I2C Demo

Brief demo project that initializes and writes text to an SSD1306 128x64 OLED over I2C. See `src/main.cpp` for the implementation.

## Using CLion
- Open the project in `CLion`.
- Recommended to use the Arduino or PlatformIO plugin for flashing and serial monitor support.
- Build/run configuration depends on your board/toolchain (Arduino CLI, PlatformIO, or custom CMake).

## IDE Version
- Tested with `CLion 2025.3.2`.

## Code Overview
- Entry: `src/main.cpp`.
- Behavior:
    - Initializes Serial at 9600 baud.
    - Initializes the SSD1306 OLED over I2C (`Wire`) at address `0x3C`.
    - Clears the display and prints a few lines of text.
    - Main loop is left empty for extension.
- Key call: `display.begin(SSD1306_SWITCHCAPVCC, OLED_ADDR);` then `display.clearDisplay();`, `display.println(...)`, and `display.display();`.

## Libraries
- `Adafruit_SSD1306`
- `Adafruit_GFX`
- `Wire` (Arduino I2C)
- `Arduino.h` (core)

Install via Arduino Library Manager or PlatformIO library registry.

## Dependencies
- Arduino core for your board (e.g., Arduino AVR, ESP32, ESP8266).
- Adafruit libraries listed above.
- I2C support from board core.

## Components used with the OLED
- SSD1306 128x64 I2C OLED module (address `0x3C` typical).
- Microcontroller board (Arduino Uno / Nano / Mega, ESP8266, ESP32, etc.).
- I2C pull-up resistors (often onboard on OLED modules).
- Jumper wires and breadboard.

## Software Requirements
- `CLion 2025.3.2`
- Arduino toolchain:
    - Arduino IDE or Arduino CLI, or
    - PlatformIO (recommended for integrated build/flash in CLion).
- C/C++ toolchain compatible with chosen board (installed via board support package).

## Hardware Requirements
- 3.3V or 5V compatible microcontroller (match OLED voltage).
- SSD1306 I2C OLED module (128x64).
- USB cable for programming and power.
- Optional: logic level shifter if MCU voltage differs from OLED module requirements.

## Author
- Ayush1Sikarwar (GitHub)
