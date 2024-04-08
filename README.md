# PipyADS1256-sample-codes
PipyADS1256-sample-codes

## Raspberry Pi4 pinlayout

<img width="817" alt="RasPi4_pin_layout" src="https://github.com/chibaf/PipyADS1256-sample-codes/assets/1296728/fd4e5228-b6ef-46fb-936d-341c132ba49b">

ref : Raspberry Pi Documentation - Raspberry Pi hardware https://www.raspberrypi.com/documentation/computers/raspberry-pi.html

## ADS1256 pin layout

![ADS1256-pins](https://github.com/chibaf/PipyADS1256-sample-codes/assets/1296728/dd428b8b-d8ed-44bb-a406-4707e179e18c)

## RasPi vs ADS1256: pin còrrespóndence between RasPi and ADS1256

GPIO#:	Description

===================

22:	Chip Select (CS)

17:	Data Ready (DRDY)

18:	RESET (GND)

27:	Power Down (PDWN)

12:	MOSI (called DIN on the slave)

13:	MISO (called DOUT on the slave)

14:	SCLK (SCK)

##  from bench_config.py

#### Raspberry Pi GPIO configuration ##########################################
# =====> NEW in version 2 since using pigpio instead of wiringpi library:
# =====> Raspberry Pi pinning now uses the Broadcom numbering scheme!
#
# Tuple of all (chip select) GPIO numbers to be configured as an output and
# initialised to (inactive) logic high state before bus communication starts.
# Necessary for more than one SPI device if GPIOs are not otherwise handled.

#CHIP_SELECT_GPIOS_INITIALIZE = (7, 8)

CHIP_SELECT_GPIOS_INITIALIZE = (7, 8)

# Chip select GPIO pin number.
# This is required as hardware chip select can not be used with the ADS125x
# devices using this library

#CHIP_SELECT_GPIOS_INITIALIZE = (7, 8)

CHIP_SELECT_GPIOS_INITIALIZE = (7, 8)

CS_PIN      = 8 # CH0

#CS_PIN      = 7 # CH1

DRDY_PIN    = 5 # CH0

CS_PIN      = 8 # CH0

#CS_PIN      = 7 # CH1

DRDY_PIN    = 5 # CH0

#DRDY_PIN    = 6 # CH1

RESET_PIN   = 3 # Set to None if not used.

# Optional power down pin

PDWN_PIN    = 2 # Set to None if not used.

DRDY_TIMEOUT    = 2

# Optional delay in seconds to avoid busy wait and reduce CPU load when

# polling the DRDY pin. Default is 0.000001 or 1 µs (timing not accurate)

DRDY_DELAY      = 0.000001


## ref:

ul-gh/PiPyADC: Python classes for interfacing Texas Instruments analog-to-digital converters with the Raspberry Pi

https://github.com/ul-gh/PiPyADC/tree/pigpio
