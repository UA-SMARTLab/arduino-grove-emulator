# Grove Kit Emulator

Program the Arduino UNO R4 + Grove kit at home, without the hardware. Made by the [SMART Lab](https://github.com/UA-SMARTLab), University of Antwerp, for the course [Elektronische aspecten van producten](https://www.uantwerpen.be/nl/personeel/abdulhamid-baghdadi_29785/onderwijs/?id=2026-1047FOWPOW&lang=nl&source=personal).

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
