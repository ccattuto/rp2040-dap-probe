# RP2040-DAP-probe

This is a simple but fully-featured implementation of a DAP probe based on the [RP2040 microntroller](https://www.raspberrypi.com/products/rp2040/)
found, e.g., in the [Raspberry Pico](https://www.raspberrypi.com/products/raspberry-pi-pico/) board. It is based on [TinyUSB](https://github.com/hathach/tinyusb)'s [hid-composite example](https://github.com/hathach/tinyusb/tree/master/examples/device/hid_composite) and inspired by [pico-debug](https://github.com/majbthrd/pico-debug).

It shows up as a USB full-speed devices supporting DAP over HID and WebUSB. Because of RP2040's 125 MHz clock speed and fast GPIO peripheral, this provides a fast and cheap DAP probe suitable for many applications.

The code was tested on a [Raspberry Pico](https://www.raspberrypi.com/products/raspberry-pi-pico/) and a [01Space RP2040-0.42LCD](https://github.com/01Space/RP2040-0.42LCD) board, using both [pyOCD](https://pyocd.io/) (HID device) and the [DAP.js](https://github.com/ARMmbed/dapjs) examples (WebUSB device).

## Configuration

- The GPIO pins used for the SWD signals (`SWDIO`, `SWDCLK` and `nRESET`) are configured [here](https://github.com/ccattuto/rp2040-dap-probe/blob/90702d241c45f48739afebc5aa52c6de312af908/inc/DAP_config.h#L298-L300).
- the USB vendor and device ID can be configured [here](https://github.com/ccattuto/rp2040-dap-probe/blob/90702d241c45f48739afebc5aa52c6de312af908/src/usb_descriptors.c#L28-L29).
- The probe's vendor and name strings can be configured [here](https://github.com/ccattuto/rp2040-dap-probe/blob/90702d241c45f48739afebc5aa52c6de312af908/inc/DAP_config.h#L157-L159).

## Building and flashing

The project depends on [CMSIS 5](https://github.com/ARM-software/CMSIS_5), which is assumed to be symlinked from the projects' main directory. Of course, a submodule will work too. Create a `build` subdirectory, and from there fun `cmake ..` followed by `make`. The resulting `dap.uf2` can be dragged & dropped to RP2040's bootloader volume. Notice: recent version of OSX break drag & drop programming, in that case use `cp -X dap.uf2 ...`. After flashing, a composite HID and WebUSB full-speed device will appear.

## License

This code is published under the [MIT license](https://opensource.org/licenses/MIT).

