In this workshop we will try to build:

- 4 Hakkaa boards...
- ...in 3 different ways...
- ...in 3 teams

The soldering and build should take around an hour, and the rest of workshop will be dedicated to flashing the firmware on the ESP32-C3 SuperMini microcontroller, exploring the embedded Rust code examples and trying to code something cool

# Project Repo's

- [Hardware](https://github.com/hakkaatachi/hakkaa-hardware): Contain's all the board design files
- [Firmware](https://github.com/hakkaatachi/hakkaa-firmware): Contain's the microcontroller firmware and some code examples and tests
- [Workshop](https://github.com/hakkaatachi/hakka-workshop): Some useful notes on coding in embedded rust from the workshop the organisers ran at Chaos Communication Congress

# Ways to Solder It

1. With a standard soldering iron

- Using standard solder on a roll
- You will need tweezers...and a third hand!

2. With our new reflow station and microscope/camera setup

- Using solder paste
- Led by anton

3. Hotplate with DIY Laser Cut Stencil

- Using solder paste
- Demo of how to export the stencil from KiCad

# Stencil Making and Using

## Making It
- We will create the stencil from the printed circuit board design files (KiCad)
- We will export the B_Paste layer and the Edge Cuts layer (board outline)
- We will cut it from thin mylar material

## Using It
- Paste should be at room temp
- Clean board with IPA before
- Tape the stencil to the board to make a liftable hinge
- Use credit card squeegee at 45 or 60 degree
- Clean stencil with IPA after
- Hopefully the stencil is thick enough to be able to apply enough paste!

# About the Microcontroller and Embedded Rust

## Microcontroller

The ESP32-C3 Super Mini is an ultra-compact, thumb-sized development board featuring a 32-bit RISC-V single-core processor clocked at 160MHz with 400KB SRAM and 4MB Flash. It provides robust wireless connectivity through integrated Wi-Fi 4 and Bluetooth 5.0 (LE), all within a tiny 22.5 mm x 18 mm footprint. Designed for modern IoT projects, the board includes a native USB-C interface for power and programming, 13 usable GPIOs, and a power-efficient deep sleep mode of approximately 43µA.

- Processor: ESP32-C3 (RISC-V) @ 160MHz.
- Connectivity: 2.4GHz Wi-Fi and Bluetooth Low Energy (BLE).
- Dimensions: 22.52 mm x 18 mm (approx. size of a postage stamp).
- I/O Pins: 11 digital GPIOs (all PWM capable) and 6 analog ADC channels.
- Communication: Supports UART, I2C, and SPI protocols.
- Power Input: 5V via USB-C or 3.3V–6V via VIN; 3.3V logic level.
- Onboard Hardware: Blue user LED (GPIO 8) and physical Boot/Reset buttons.
- Design: Single-sided PCB layout, ideal for both breadboarding and SMD surface mounting.

## Installing Embedded Rust (Toolchain)

We need to install rust via rustup and install the toolchain to compile for the ESP32 chip on the microcontroller.

Basic details are in the [Firmware](https://github.com/hakkaatachi/hakkaa-firmware) repo and you can also follow [Dinis's notes](./Dinish_Firmware_Instructions.md) for a step-by-step style guide.

Rust's 'cargo' command makes pulling in the relevant packages really easy

## Embedded Rust Language and Code Examples

- [The slides in this repo](https://github.com/hakkaatachi/hakka-workshop) are a good starting point, we can go through them together

The basics are:
- In Embedded Rust we have no access to rust standard library
- Embassy is used for async and concurrency
- We have blinky, smile, shake and hardware tests in the [firmware repo examples folder](https://github.com/hakkaatachi/hakkaa-firmware/tree/master/examples) and they are fairly simple to understand
- The firmware itself is also written in rust and is more complex
- [This](https://github.com/rust-embedded/awesome-embedded-rust) is a useful repo of curated Embedded Rust resources

- Let's try to code something cooler than the basic examples provided!
