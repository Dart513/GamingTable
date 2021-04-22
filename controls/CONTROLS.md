# Controls
The interface between hardware and software is a Python3 project which maps GPIO inputs to keys. This Python3 project only works properly on Raspberry Pis which run 
operating systems with apt-get.  
  
The control scheme can currently support ADS1015 and Raspberry Pi GPIO Inputs.
  
## keymap.json  
[keymap.json](https://github.com/Dart513/GPIOKeybind/blob/0023cc2e6034bcb291e29f559dd56cadd3914577/keymap.json) is a file which allows you to define the mappings between hardware
inputs and keyboard inputs. So far, it supports:
- GPIO
- ADS1015

### Universal Properties:
The JSON file is set up in the format of an array of objects. Each object must have the following properties:  
- "name"
  - The name of the input
- "interface"
  - Which method of hardware input you use, e.g. "ADS1015" or "GPIO"
- "type"
  - What type of keyboard input you want to map the input to, e.g.
    - "BUTTON": a button
    - "DOUBLE_AXIS": Joystick which binds to a PWM input of two keys
- "source"
  - Either for GPIO, which GPIO input the button is bound to or for ADS1015, which channel the analog input is plugged into
  
### Type-Specific Properties:  
Based on the type of input, the object will require different properties.  
  
"BUTTON":
- "inverted": boolean
- "binding": String (which key(s) are to be pressed)

"DOUBLE_AXIS":
- "bindMin": Which binding for the lower bound of the axis
- "bindMax": Which binding for the higher bound of the axis
- "inMin": Minimum analog input
- "inMax": Maximum analog input
- "GAIN": Recommended 1 for 3.3V devices
- "deadzone": Deadzone size (goes from 0-2)
  
   
  
For an example keymap.json, check out the provided [example](https://github.com/Dart513/GPIOKeybind/blob/0023cc2e6034bcb291e29f559dd56cadd3914577/exampleKeymap.json) 
