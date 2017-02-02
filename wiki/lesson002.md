#Change Blinky

The Arduino IDE comes with a few sample programs that they call 'sketches.'  Blinky is about the most simple that there is.  Load blinky in the Ardunio IDE and look at the code.  Chances are you are familiar enough with various coding languages to realize that content between /*  and */ are comments and can be though of as the programmer talking to other humans looking at the code.  This also goes for anything after double slashes on a single line as shown below.
```
/* this
is 
a
multi line comment */

//this is a single line comment

this line is not a comment and will break your program
```

So looking at the structure of blinky, we can ignore all of the comments, or even highlight and delete them if you like.  We are left with 9 separate lines of C code. I am able to paste it below here as if you read the comments you will see the author said that the code was in the public domain.
```
void setup() {
  pinMode(LED_BUILTIN, OUTPUT);
}
void loop() {
  digitalWrite(LED_BUILTIN, HIGH);  
  delay(1000);                       
  digitalWrite(LED_BUILTIN, LOW);    
  delay(1000);                        
}
```
Without the comments it is not completely obvious what each line does until you have played/learned C and Arduino constants, functions, and program structure.  I highly suggest reading the original 36 line program with all comments to get an understanding of what each and every line is for.  Done yet? I am serious. Go read the code and then come back here.  Go play with the code, change things, reflash your device a few times with some changes and get a feel for what is going on.

After reading the code and the comments, there are a few things that non programmers might still feel a bit confused about.  At a high level, `void setup() {` and `void loop() {` are called functions, and the syntax that is required is to specify the return type, the name of your function, what values you are passing into the function, and then the { begins the wrapping of more code that is contained in your function.  Looking at `void setup() {` we can see the function is named setup, void is the return type, nothing is passed into it in the empty (), and it has an open curly brace that has a matching closing curly brace after just a single line of contained code.  Void is a fancy word for saiing nothing - this function takes no input, returns no output, but the single line of code within it does some work setting up a pin named LED_BUILTIN to be an output pin. 
[pinMode](https://www.arduino.cc/en/Reference/PinMode) is the documentation for exactly what is being done in our program setup() function.  You should also read about [digitalPins](https://www.arduino.cc/en/Tutorial/DigitalPins) which is a link from the pinMode page.

Code execution is for the device to run setup() just once when it is first turned on, and then repeat the loop() function until power is removed or some error condition occurs. 

* Play with the delays for the duration the LED is on or off.  
* Try playing with the internal pullup resistor you read about in the digitalPins to see if you can get a dim LED state
* Try adding an external LED from an arbitrary digital pin, to a resistor, to ground, and changing the pinMode to get your external LED to light up.  Note that LED's are called polarized components because it only works in one direction. LED stands for light emitting diode and a diode is a devide that only allows electricity to flow in one direction.  If you cannot get your LED to light, make sue you have it in correctly by wiring it from your VCC pin, through a resistor to ground. Choose a resistor value with the help of the pinMode link above ( You did read that by now, right?)
* Try running the LED from the same pin, to the same resistor, and to VCC now and see what has changed.  You might need to adjust your delays to be able to tell which state HIGH vs LOW is which by making them very different durations. 100 and 1000 can be good starting points.
* keep playing! Worst case is you break something, none of this is expensive to play with, and chances are you wont make the same mistake too many times!
