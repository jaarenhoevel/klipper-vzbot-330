# Klipper MCU Update

## Toolhead:
- Micro-controller Architecture = STMicroelectronics STM32
- Processor model = STM32G0B1
- Bootloader offset = 8KiB bootloader
- Clock Reference = 8 MHz crystal
- Communication interface = CAN bus (on PB0/PB1)
- (1000000) CAN bus speed

`make clean & make`

`cd ~/katapult/scripts`

`python3 flashtool.py -i can0 -f ~/klipper/out/klipper.bin -u 4d63cfc036f3`

## Main:
- Micro-controller Architecture (STMicroelectronics STM32) ---> 
- Processor model = STM32G0B1
- Bootloader offset = 8KiB bootloader
- Clock Reference = 8 MHz crystal
- Communication interface = USB to CAN bus bridge (USB on PA11/PA12)
- CAN bus interface = CAN bus (on PD12/PD13)

`make clean & make`

Put board in dfu mode (reset, boot btn)
    
`sudo dfu-util -a 0 -d 0483:df11 --dfuse-address 0x08002000 -D ~/klipper/out/klipper.bin`
