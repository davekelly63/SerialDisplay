# SerialDisplay
Uses STM32F7 demo board with LCD as a serial terminal display

STM32F769I Discovery board comes with 4" capacitive touchscreen LCD

It is fitted with sockets for Arduino, these are used for external input.

Serial data is received on the UART connection and displayed on the LCD

Also available is I2C display features.

##Protocol##

###Monitor Mode###
In monitor mode, data is displayed directly on the LCD. Special control characters are not interpreted, except LF and CR

###Graphics Mode###
A simple display interpreter language is used to create simple graphics.

The primitives are:

Parameters are separated by space or comma. Terminate with CR or LF

Primitive | Parameters | Description
GOTO | x, y | Move current position to x, y. origin 0, 0 is top left hand corner
COLOR | r, g, b | Set the current color to rgb value
SQUARE | x, y, width, [FILLED/UNFILLED] | Draw a square at position, filled in current color or outline only (default if not supplied is unfilled)
CIRCLE | x, y, radius, [FILLED/UNFILLED] | draw a circle with centre at x, y. Default is unfilled
