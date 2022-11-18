# RP2040-DAP-probe

This is a simple but fully-featured implementation of a DAP probe based on the [RP2040 microntroller](https://www.raspberrypi.com/products/rp2040/)
found, e.g., in the [Raspberry Pico](https://www.raspberrypi.com/products/raspberry-pi-pico/) board. It is based on [TinyUSB](https://github.com/hathach/tinyusb)'s [hid-composite example](https://github.com/hathach/tinyusb/tree/master/examples/device/hid_composite) and inspired by [pico-debug](https://github.com/majbthrd/pico-debug).

This has been tested with a [Raspberry Pico](https://www.raspberrypi.com/products/raspberry-pi-pico/) boand and a [01Space RP2040-0.42LCD](https://github.com/01Space/RP2040-0.42LCD) board.

## Configuration



## Building

The project depends on [CMSIS 5](https://github.com/ARM-software/CMSIS_5), which we assume is symlinked from the projects' main directory.


## License

This code is published under the [MIT license](https://opensource.org/licenses/MIT).

