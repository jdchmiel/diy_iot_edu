# Power Wheel Speed Governor - rev 1

## Design goals
The initial revision of this controller will intercept the battery on a 6v rated powerwheel device to provide a PWM output to the motors. This PWM signal is desired in order to lower the top speed attained when using a 12v SLA battery in place of the 6v battery.  

### Electronic Brake
The specific powerwheel model in question has a 2 position foot activated button that directly connects the battery to the motors when depressed, and disconnects the battery while not depressed.  The 'off' state also shorts the motor leads together to provide a very effective electric brake.  The brake functionality must be preserved for safety.  This design seeks to only be in use while the foot switch is depressed in order to avoid any changes to the braking system.

### Smooth Start
Using the 12v battery in the 6v system has a few downsides. One downside is that with a simple 'on' switch, the initial jolt of acceleration causes children who have climbed onto the back of the unit to fall off.  On smooth driveway surfaces the initial jolt combined with low traction hard plastic wheels merely causes agressive wheelspin.  In order to lessen the severity and possibly entirely mitigate these two scenarios, the PWM signal can be ramped from a 0% duty cycle to the desired duty cycle over the course of some time interval. This ramp up time will be a hard coded constant in the code for revision 1.  An initial value of 1 second will be tested.

### Top Speed
The 12v battery proves 4x the power to the motors as the 6v battery.   In a perfect system with no losses this should make the top speed twice as fast.  The factory speed is rated at 3.5 mph, and to be safe for ages 2+.  My 4 year old loves the 7mph doubled speed, but my 2 yr old and special needs 6 yr old are unable to drive it in its current state due to the on/off nature and the higher top speed.  The goal is to set a duty cycle that provides a lower speed for the other two children to get used to and feel comfortable with, before allowing for a higher top speed. Battery life should also be increased substantially by reducing the power.  For revision 1, the duty cycel for governed top speed will be a hard coded constant in the code.

