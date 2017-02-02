#First Lesson:
Goal is to use the Ardunio IDE to program an ardunio.  Some of us do not have a regular arduino that has USB port so there are alternate ways.
##CAUTION
Please be aware that electricity can hurt things. If you progress past the 'easy' step below, ensure that you are using matching voltage on your devices.  The common voltages are 3.3v and 5v.  There are some 1.8v, 2.5v and other chips out there but they are much less common in the arduino maker space.  If you mix 3.3 and 5v devices you can fry them.  Until you understand the differences, it is best to just match the voltages of the devices that you wire together.



###EASY
Plug your device into your computer. Open the Arduino IDE, choose your board, and flash the sample blinky program to your board.

###ALSO EASY
If you have an FTDI cable or dongle - Plug the USB cable into dongle, plug dongle to your device, and flash the sample blinky program.

###HARDER
If you cannot plug a USB cord into your device as it has no FTDI or equivilent, but you DO have another device that has TX, RX, reset, VCC, and ground pinds available, you can use the usb to serial conversion mechanism from that device to program your target device.  The original Ardunio Uno is a good example of this where the arduino board has an FTDI chip on it, and the Atmega microprocessor is a dip chip that can be removed from the socket.  This allows you to use the bare board as a pass through FTDI basically.  The only reason this is harder than the previous method is that you have to find the pins and jumper them all individually.
I followed this tutorial: http://www.instructables.com/id/Uploading-sketch-to-Arduino-Pro-Mini-using-Arduino/?ALLSTEPS
And was able to program blinky onto two arduino pro mini boards, as well as the Arduino Uno once I put the chip back into it.

Total time was about an hour for me, including finding the soldering iron, soldering them to the mini's, making jumper wires out of an old PC CD ROM audio cable, and then doing the actual flashing.


###HARDEST
The most difficult way is when you have a device such as a Raspberry Pi or an Ardunio where the atmega microprocessor cannot be unplugged from a socket to remove it from circuit..  Some devices might have a jumper to remove power to the on board chip to allow you to pass through program like the previous method, but the majority will require you to do a twp step flashing method.  You will need to use google on your own to find a tutorial for this.  At a high level you will flash a programmer application to your device with a USB interface turning it into a programmer.  You will then provide power, ground, reset, tx, and rx for the target board.  Your programmer tutorial may choose any suitible pin on your pgrommer device for tx and rx, so you will have to wire carefully.

#TAKEAWAY
Flashing your target device is the baseline process you will need to do repeatedly as you prototype and learn.  You should understand what tx, rx, vcc, ground, reset pins are for, even if you are able to resort to the 'easy' method above from now on.  You should understand that google will be a constant companion of yours through all of this - this repository is more of a self directed path for you to take, not an all encompassing education resourceto hold your hand.
