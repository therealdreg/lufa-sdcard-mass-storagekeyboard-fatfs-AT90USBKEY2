# -
# David Reguera Garcia aka Dreg - dreg@fr33project.org - https://github.com/David-Reguera-Garcia-Dreg - http://www.fr33project.org
#
# ported from LUFA_091223 http://www.fourwalledcubicle.com/LUFA.php
# to lufa-LUFA-170418
#
# ported from Mathieu Sonet lufa-sdcard-mass-storage-demo USB Mass storage on SD card with a Teensy2/ATMEGA32U4 https://bitbucket.org/elasticsheep/lufa-sdcard-mass-storage-demo/src/default/
# to AT90USBKEY2 at90usb1287
#
# ported from http://www.roland-riegel.de/sd-reader/index.html MMC/SD/SDHC card reader library 
# to FatFS - Generic FAT Filesystem Module - http://elm-chan.org/fsw/ff/00index_e.html
# -
#
#             LUFA Library
#     Copyright (C) Dean Camera, 2017.
#
#  dean [at] fourwalledcubicle [dot] com
#           www.lufa-lib.org
#
# --------------------------------------
#         LUFA Project Makefile.
# --------------------------------------

# Run "make help" for target help.

MCU          = at90usb1287
ARCH         = AVR8
BOARD        = USBKEY
F_CPU        = 8000000
F_USB        = $(F_CPU)
OPTIMIZATION = s
TARGET       = MassStorageKeyboard
SRC          = $(TARGET).c Descriptors.c \
                Lib/SDCardManager.c Lib/diskio.c \
				Lib/mmc_avr_spi.c Lib/SCSI.c \
				$(LUFA_PATH)/Drivers/Peripheral/AVR8/Serial_AVR8.c \
				$(LUFA_SRC_USB) \
				$(LUFA_SRC_USBCLASS)
LUFA_PATH    = ../../../../LUFA
CC_FLAGS     = -DUSE_LUFA_CONFIG_HEADER -IConfig/
#CC_FLAGS     = -DENABLE_DEBUG -DUSE_LUFA_CONFIG_HEADER -IConfig/
#CC_FLAGS     = -DNO_LEDS -DNO_JOYSTICK -DUSE_LUFA_CONFIG_HEADER -IConfig/
#CC_FLAGS     = -DENABLE_DEBUG -DNO_LEDS -DNO_JOYSTICK -DUSE_LUFA_CONFIG_HEADER -IConfig/
LD_FLAGS     =

# Default target
all:

# Include LUFA-specific DMBS extension modules
DMBS_LUFA_PATH ?= $(LUFA_PATH)/Build/LUFA
include $(DMBS_LUFA_PATH)/lufa-sources.mk
include $(DMBS_LUFA_PATH)/lufa-gcc.mk

# Include common DMBS build system modules
DMBS_PATH      ?= $(LUFA_PATH)/Build/DMBS/DMBS
include $(DMBS_PATH)/core.mk
include $(DMBS_PATH)/cppcheck.mk
include $(DMBS_PATH)/doxygen.mk
include $(DMBS_PATH)/dfu.mk
include $(DMBS_PATH)/gcc.mk
include $(DMBS_PATH)/hid.mk
include $(DMBS_PATH)/avrdude.mk
include $(DMBS_PATH)/atprogram.mk
