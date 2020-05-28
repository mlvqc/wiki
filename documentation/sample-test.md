# Testing a sample at room temperature

{% hint style='danger' %} Warning: not all samples should be tested at room temperature. Some samples could be damaged by even the very weak electronics in this testing procedure. Check before you test it that this isn't the case for your sample! {% endhint %}


1. Make sure the puck is grounded on the top side (you'll need to remove the bottom side to get it into the room temperature testing rig. Do this after grounding the top side!). 
2. Load the puck into the testing rig. 
3. Look at the Keithley settings. In quick setup (or something like that) make sure the voltage source is set to 1 mV or less and there is a current limiter on. 
4. We can test the Keithley output by plugging the coax output into a breakout pin that is grounded. Check the resistance is correct. (We are measuring the current through ground). At this stage the device still has its shorting pin in. 
5. Saftey check: plug the wire into a pin that is not connected to a device. When it is ungrounded, we should see a current. When we then remove the short and try again, we should see no current. 
6. Plug the Keithley into the source. The drain should be on ground. Float the source and we should measure a current. This is the current through the device. 
7. We can then check gates for leakage. Float them all and one by one ground them to see if there is current from high voltage (source) to ground (the grounded gate). 
