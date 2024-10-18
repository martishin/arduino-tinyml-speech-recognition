# Arduino TinyML Speech Recognition

This example shows how to run a 20 kB ML model that can recognize 2 keywords,
"yes" and "no", from speech data.

The application listens to its surroundings with a microphone and indicates
when it has detected a word by lighting an LED or displaying data on a
screen, depending on the capabilities of the device.

The code has a small footprint (for example, around 166 kilobytes on a Cortex
M4) and only uses about 54 kilobytes of additional RAM for working memory.

## Tested Devices

The example has been tested with the following devices:

- [Arduino Nano 33 BLE Sense](https://store.arduino.cc/usa/nano-33-ble-sense-with-headers)

The Arduino Nano 33 BLE Sense is currently the only Arduino with a built-in
microphone. If you're using a different Arduino board and attaching your own
microphone, you'll need to implement your own `audio_provider.cpp` code. It also has a
set of LEDs, which are used to indicate that a word has been recognized.

## Running Locally

This project uses [PlatformIO](https://docs.platformio.org/en/latest/), you can load it in any IDE that supports it, for example [Visual Studio Code](https://code.visualstudio.com/) or [Clion](https://www.jetbrains.com/clion/).
You can also use [Arduino IDE](https://www.arduino.cc/en/software).

Use the IDE to build and upload the example. Once it is running, you should see the built-in LED on your device flashing. 
Saying "yes" will cause the green LED to light up, while saying "no" will cause the red LED to light up. 

The program also outputs inference results to the serial port, which appear as
follows:
```
Heard yes (201) @4056ms
Heard no (205) @6448ms
Heard unknown (201) @13696ms
Heard yes (205) @15000ms
```

The number after each detected word is its score. By default, the program only
considers matches as valid if their score is over 200
