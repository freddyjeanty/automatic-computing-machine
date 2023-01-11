# Automatic Computing Machine [IOT Project] 
## Descrition:

Developpement d'un système de surveillance pour votre maison qui utilise plusieurs capteurs pour détecter des intrusions, mesurer la température et l'humidité, et surveiller l'état des portes et fenêtres.

## HW Setup:
- Un STM32 
- Des capteurs de mouvement, de température, d'humidité, et d'état de porte/fenêtre
- Des câbles et connecteurs pour relier les capteurs au STM32.

## SW Setup:
- Install gcc-arm-none-eabi (to compile source code)
- Install st-flash dependancy using apt-get install libusb-1.0-0-dev
- Install st-flash:
    - sudo apt-get install pkg-config debhelper
    - Go to https://github.com/stlink-org/stlink/releases and
    wget the stlink_1.7.0-1_amd64.deb on your local machine using the url link:
        - wget https://github.com/stlink-org/stlink/releases/download/v1.7.0/stlink_1.7.0-1_amd64.deb
        - sudo dpkg -i stlink_1.7.0-1_amd64.deb

## General architecture for an STM32 project:

    Initialization:
        Set up the clock and system peripherals
        Initialize any on-board devices or peripherals
        Initialize any external devices or peripherals

    Main loop:
        Read sensor data and/or inputs
        Perform any necessary processing
        Update any outputs or displays
        Go to sleep or idle until the next iteration

    Interrupt service routines (ISRs):
        These are functions that are called when certain events or interrupts occur
        They can be used to handle asynchronous events, such as data arriving from a sensor or a timer expiring

    Functions:
        These are blocks of code that perform specific tasks, such as reading a sensor or updating an output
        They can be called from the main loop or from ISRs as needed


## How to contribuite to this project
- Have the HW setup ready
- Create your developement workspace
- Clone this project to your workspace (within a virtual env is posible)
- Create your "dev" branch and do your magic
- Create a merge request on the master branch


# How to check, compile and flash your STM32
Let's say that your project looks like this:
```
main.c
Makefile
stm32f411re.ld
```
## Check if STM32 is visible:

``` st-info --probe ```

## Build:
Run the make commande

``` make ```

After running the make command, check your workspace. Now it's should look like this:

```
main.bin
main.c
main.elf
main.o
Makefile
stm32f411re.ld
```

## Flash
Deploy your programm on your device
``` st-flash write main.bin 0x8000000 ```

## This is a simple exemple, it will be completed gradually
