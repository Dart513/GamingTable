# PCB

The PCB for this project is a single-sided PCB designed to avoid a rat's nest of jumper cables. It accepts a [Raspberry Pi ribbon cable](https://www.sparkfun.com/products/13028) in the center connector.
The Raspberry Pi pins are then broken out to an [ADS1015 ADC](https://www.adafruit.com/product/1083) through I2C and several GPIO inputs.  
  
To open this project in Fritzing, it is necessary to first import the custom part [Adafruit Header - 40 Pins.fzpz](https://github.com/Dart513/GamingTable/blob/main/pcb/Fritzing/Adafruit%20Header%20-%2040%20pins.fzpz)  
  
Buttons and joysticks are meant to be soldered into the locations marked on the PCB, but connectors also work for less permanent installations.  
The joysticks connect to the ADS1015.  
  
All of the GPIO buttons have pull-down resistors attached to them.  
