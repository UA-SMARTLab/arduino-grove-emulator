# Grove Kit Emulator

Program the Arduino UNO R4 + Grove kit at home, without the hardware. Made by the [SMART Lab](https://github.com/UA-SMARTLab), University of Antwerp, for the course [Elektronische aspecten van producten](https://www.uantwerpen.be/nl/studeren/aanbod/alle-opleidingen/productontwikkeling-studeren/master/schakelprogramma/studieprogramma/?id=2026-1047FOWPOW&lang=nl).

**Open it:** https://ua-smartlab.github.io/arduino-grove-emulator/ (works best in Chrome or Edge)

## For students

1. Write your sketch in the editor, just like in the Arduino IDE, or pick one from **Examples**.
2. **Connect your modules:** each module card has a port menu. Choose the port you would plug the Grove cable into
   (for example the button on D2, the LED strip on D6, the LCD on I2C). Nothing is connected until you do.
3. Click **Upload & run**. Your code is compiled by a real C++ compiler; if it has an error, it is not uploaded and the line is highlighted.
4. Use the modules on screen: hold the button, drag the sliders and the joystick, tilt the IMU. Watch the serial monitor, the plotter, the LEDs, the servo and the LCD.

The EAVP exercises are in **Examples → EAVP exercises (start code)**; the task text appears above the editor.

The first upload downloads the compiler once (about 23 MB) and can take 15–30 seconds; after that an upload takes under a second.

## What is simulated

Button, touch sensor, buzzer, servo, NeoPixel LED strip, rotary and slide potentiometer, light, temperature and sound sensor,
joystick, RGB LCD (`rgb_lcd.h`), AHT20 temperature & humidity (`AHT20.h`), 9DOF IMU (`ICM20600.h` + `AK09918.h`),
Serial monitor and plotter.

## How it works

The sketch is compiled with clang (LLVM, running in the browser as WebAssembly) together with an Arduino core and the kit's
libraries written in C++. The compiled program runs in the page and talks to a model of the kit. Without internet, or in a browser
that cannot run compiled programs, a simpler simulator runs the code instead (it does not support all of C++).

It is a learning tool: timing and electrical details are not exact, so always test on the real kit too.

## Credits and trademarks

- The C++ compiler is [LLVM/Clang](https://llvm.org/) (Apache-2.0 with LLVM exception), built for the browser by
  [YoWASP](https://github.com/YoWASP/clang) and loaded from jsDelivr when the page runs; it is not part of this repository.
- The Arduino core and the kit libraries inside the emulator are our own implementations that follow the official
  interfaces (Arduino, Seeed Studio, Adafruit), so the same sketches compile. No library code is copied.
- The exercises come from the course *Elektronische aspecten van producten* at the University of Antwerp.
- Arduino, Grove, Seeed Studio and Adafruit are trademarks of their owners. This project is a teaching aid of the
  University of Antwerp and is not affiliated with or endorsed by them.

## Licence

The emulator code is released under the [MIT licence](LICENSE). The course exercises and the University of Antwerp
logo are not covered by it.
