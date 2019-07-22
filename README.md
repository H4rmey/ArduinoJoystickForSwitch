# ArduinoJoystickForSwitch

First git project i setup myself pls don't hate :) 

## Intro
I wanted to make a controller for the switch using a microcontroller (arduino). So i started looking for an easy way to do so. What i found was that it was not as easy as i first thought. So i decided to make it easier for other people (at least that is the plan).

This project is made for the arduino pro micro (because i had a lot of them and wanted to use them in a project) and the arduino leonardo. You can also use this for a teensy or the arduino UNO, but for that you'll need to dive into the repositories i used yourself. It should also work for the arduino micro, if you're using a arduino micro follow all the same steps for the leonardo because the layout is very similar.

I use this repository as my main setup:	https://github.com/wchill/SwitchInputEmulator <br/>
I used this repository as an example/setup: https://github.com/progmem/Switch-Fightstick <br/>
They used this library to tie it all together: http://www.fourwalledcubicle.com/LUFA.php <br/>
(huge credit to these guys, i have no clue how this works but it does)

## Upload to arduino
If you simply want the program and don't want to look at/compile the code yourself, thats fine! You'll simply have to upload the Joystick.hex file in the Arduino Pro Micro/Arduino leonardo folder.
### Linux
1. install arduino IDE or setup the AVR toolchain
2. plug in your arduino pro micro/leonardo
3. open the terminal in the Arduino Pro Micro or Arduino Leonardo folder (depending on what which
arduino you use ofcourse)
4. use the following command: 
```bash
avrdude -C"/usr/share/arduino/hardware/tools/avrdude.conf" -v -patmega32u4 -carduino -b57600 -cavr109 -P/dev/ttyACM0 -D -Uflash:w:Joystick.hex:i
```
5. profit...?

p.s.: if the command gives an error try pressing the reset button on the arduino right before executing the command (sometimes it takes 1-5 tries to upload for me...). or try to change the path to the avrdude/avrdude.conf.

### Windows
idk prob use Xloader to upload the hex file (im not on windows so idk how that works...)

## editing code setup
If you are on Linux you can also change the if you want to (you can also do it on Windows
but i'll be honest i have no idea how because im on Linux D:). 
1. Install the arduino IDE or setup the AVR toolchain. 
2. Install the GCC compiler and Tools: https://www.pjrc.com/teensy/gcc.html or use sudo apt-get install gcc-avr binutils-avr avr-libc. 
3. Go into the pro micro/leonardo directory. 
4. Open Joystick.c and edit the code however you like i guess. 
5. Open a terminal in the pro micro/leonardo directory and type the command: ```make``` his will generate a new Joystick.hex. 
6. Follow the instructions for linux above. 

## mapping
Button mapping (pro micro):<br/> 
D0:<br/>
D1:<br/>
D2:<br/>
D3:<br/>
D4:<br/>
D6:<br/>
D8:<br/>
D9:<br/>
D10:<br/>
D14:<br/>
D15:<br/>
D16:<br/>

Button mapping (leonardo):<br/> 
D0:<br/>
D1:<br/>
D2:<br/>
D3:<br/>
D4:<br/>
D6:<br/>
D8:<br/>
D9:<br/>
D10:<br/>
D11:<br/>
D12:<br/>
D13:<br/>

## welp...
The +, -, home, capture and analog sticks do not work, due to either not enough inputs (hardware limitations) or me not knowing how you can use the avr library to read out analog pins (if someone could explain by a piece of example code, that would be lovely and highly papriciated).


sorry for bad english

