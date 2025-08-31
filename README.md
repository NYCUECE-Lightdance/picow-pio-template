# Raspberry Pi Pico W Template for Lightdance

A development template for Raspberry Pi Pico W using the Arduino framework.  
Refer to [Using this core with PlatformIO](https://github.com/earlephilhower/arduino-pico/blob/master/docs/platformio.rst) for more details about the setup.

## Getting started

### Install PlatformIO IDE Extension for Visual Studio Code

1. Open Visual Studio Code
2. Click on the Extensions icon on the sidebar
3. Search for "PlatformIO IDE"
4. Click "Install" to install the extension
5. Restart VS Code

### Clone the Repository

Open Command Prompt or PowerShell and run the following commands:

```bash
git clone https://github.com/NYCUECE-Lightdance/picow-pio-template.git
cd picow-pio-template
```

### Open the Project in VS Code

1. Open Visual Studio Code
2. Click "File" → "Open Folder"
3. Select the `picow-pio-template` folder you just cloned
4. Click "Select Folder"  

PlatformIO IDE will automatically detect the project and install the necessary dependencies.

## Build and Upload

### Connect Hardware

Make sure your Raspberry Pi Pico W is connected to your computer in BOOTSEL mode:  
1. Prepare a USB cable
2. Hold down the BOOTSEL button on the Raspberry Pi Pico W
3. Connect the USB cable to your computer, then release the BOOTSEL button

Notice that you may need the [Zadig tool](https://zadig.akeo.ie/) to install the USB driver for the Pico W.

### Build Project

In VS Code:

1. Click "Build" in the PlatformIO panel
2. Or use the keyboard shortcut: `Ctrl + Alt + B`

An alternative command line method is to run:
```bash
pio run
```

All the dependencies will be automatically installed during the first build.

### (Build and) Upload Program

You can (build and) upload the program after building:

1. Ensure the Pico W is properly connected and in BOOTSEL mode
2. Click "Upload" in the PlatformIO panel
3. Or use the keyboard shortcut: `Ctrl + Alt + U`

An alternative command line method is to run:
```bash
pio run --target upload
```

Sometimes you may need to manually set the serial port when uploading.  

### Monitor Output

If you need to view serial port output:

1. Click "Monitor" in the PlatformIO panel
2. Or use the keyboard shortcut: `Ctrl + Alt + S`

An alternative command line method is to run:
```bash
pio device monitor
```

## Project Structure

```
picow-pio-template/
├── platformio.ini      # PlatformIO configuration file
├── src/               # Main source code
│   └── main.cpp       # Main program file
├── include/           # Header files directory
├── lib/               # Local libraries directory
├── test/              # Test code directory
└── README.md          # Project documentation
```

## Configuration

### platformio.ini Settings

- `platform`: Uses Raspberry Pi platform
- `board`: Specifies pico development board
- `framework`: Uses Arduino framework
- `board_build.core`: Uses [arduino-pico](https://github.com/earlephilhower/arduino-pico) from earlephilhower
- `lib_deps`: Required libraries

The flash size of Raspberry Pi Pico W is `2MB`.  
Currently, we split the storage as `Sketch: 1MB`, `FS: 1MB`.

### Dependencies

- **EasyButton** - Simplified button operations
- **ArduinoJson** - JSON data processing
- **FastLED** - For WS2812 LEDs control
- **Adafruit SSD1306** - OLED display driver

## Start Developing

The `src/main.cpp` file is where the main application code resides.  
Remember to include `Arduino.h` at the top of your `main.cpp` file to access Arduino functions and features.  