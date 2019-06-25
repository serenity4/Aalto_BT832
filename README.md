# Description

Repository for the Bluetooth module BT832 programming used for ADCS simulations at Aalto University.

# Bluetooth module BT832

Programming was done using the Nordic SDK on a Windows environment. The code developped is an adaptation of the ble_app_uart example provided in the Nordic SDK.

# Getting started

## Setup

If you don't have it, get the following:
- nRF Command Line Tools (nrfjprog) + JLink Software available on the <a href='https://www.nordicsemi.com'>Nordic official website</a>
- Nordic SDK 15.3.0 also available on <a href='https://www.nordicsemi.com'>their website</a>
- GNU Tools for ARM Embedded Processors 4.9 2015 or higher
- Make for Windows 3.81 or higher <br>

Then, go to `<SDK folder>/examples/ble_peripheral/ble_app_uart` and replace the file `main.c` by the file provided in this repository. Do the same for the file `sdk_config.h` located at `<SDK folder>/examples/ble_peripheral/ble_app_uart/pca10040/s132/config`.
<br>
To be able to compile the file and to flash it, we need to provide the Makefile with environment specific options. Navigate to `<SDK folder>/components/toolchain/gcc` and edit these lines on the file `Makefile.windows` based on your own configuration, for example: <br>
`GNU_INSTALL_ROOT := D:/Software/GNU_ARM_4.9-2015-q3/4.9 2015q3/bin/`<br>
`GNU_VERSION := 7.3.1` <br>
`GNU_PREFIX := arm-none-eabi` <br>

## Compiling and flashing the code

Compiling and flashing are done at the same time. Simply navigate to the folder that contains the Makefile, i.e. 
`<SDK folder>/examples/ble_peripheral/ble_app_uart/pca10040/s132/armgcc`, and from the Command Prompt (or Powershell) 
execute the command `make flash`. Note that if you erase the board with `make erase` or `nrfjprog --eraseall`, you will need need to flash
the 
SoftDevice with `make flash_softdevice` before flashing your code. This SoftDevice is an essential component for the module
and your program will not work if it is not flashed into the device.





