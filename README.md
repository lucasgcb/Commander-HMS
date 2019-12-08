This repository implements the Commander interface for controlling a step motor utilizing [EasyDriver](https://www.schmalzhaus.com/EasyDriver/) and an STM32F103C8T6 Blue Pill Board. 

This has been developed using the [STM32CubeMX IDE by STM](https://www.st.com/en/development-tools/stm32cubeide.html).

The clock configuration is 48MHz. It uses FreeRTOS.

### Pinout

The pinout is configured as follows:

![pins](./doc/img/pinout.png)

### Implementation

The state machine and commands available as as follow:

![machine](./doc/img/machine.png)

Send commands by connecting to the microcontroller through the COM serial interface.
You can use [Python](https://pyserial.readthedocs.io/en/latest/) or something like [Terminalbpp](https://sites.google.com/site/terminalbpp/) for that.

Commands for changing step values:

*SSTPX(num)
*SSTPY(num)

Response: the new step for the chosen axis 

Commands for checking step:

*STPX
*STPY

Response: the current step for the chosen axis 

### Showcase 

[HMS-X Scanner](https://github.com/lucasgcb/CEM-Scanner-HMS-X) - A project that utilizes this interface to control three motors in a dual axis automation hub for automatic measurement of printed circuit boards.
