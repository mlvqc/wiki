SETTING UP REFLECTOMETRY: A COMPLETE USER GUIDE                         2019-12-12
-----------------------------------------------                         ----------

JDH 
BS 
NvE

---

## 1 | Preamble 

The device is already loaded and the fridge is already cold. If you find yourself disagreeing with either of these statements, look for a different document. 

Fridge wires are plugged in and ungrounded. Follow the bonding scheme and fridge diagram for help with this.   



## 2 | Loading IGOR 7 PRO

    a) Initialise the following procedures: 
        1) OxDataInit() # Opens the window for selecting channels and sets up a lot of stuff. 
        2) InitDAC() # opens the DACtable and initialises the DACs. 
        3) setval("call", 0) # Sets all the DAC values to 0. 
        4) initscaleATS() # Initialises the Alazar card.
        5) InitFlorianGUI() # Opens windows that facilitates easy sweeps. 
        6) VISAinit() # Initialises the VISA device management to allow connection over GPIB.
        7) EXAinit() # Driver for the EXA device (Agilent Tech. signal analyser).
        
    b) Set gainSQUID as channel 1 measurement.  


## 3 | Set up apparatus for tuning squid. 

    a) The maximum power into the fridge is approximately -20 dBm. Make sure that, between the power sent in by the signal generator/lock-in and any in-series attenuators, you are not exceeding this value at the fridge. 

    b) The frequency at which the SQUID is tuned is selected based on the frequency of the device cavity. This is seen as a large dip on the spectrum analyser when the reflected power from the device is measured. 
    
    c) The frequency of this dip can be altered with a functioning varactor. If the varactor is not working then the frequency is not variable. 
    
    d) Plug A6 into the frequency generator and RX into the RF input on the signal analyser. To use the room temperature amplifier, plug RX cable into 'Rx' on the demodulation box and then run a wire from 'Sig Mon' (on the demodulation box) to the input of the signal anaylser. [See fridge diagram for clarity].
    
    e) Ensure cryoamp is on. To turn it on, turn the dial on the cryoamp power box (labelled TRITON 1 LAVYPOWER 2) [nomenclature unclear] to 5. This is the maximum. Turn the dial ANTICLOCKWISE to increase the power. 
    
    f) Bandwidth on EXA should be very low - in the few Hz range (3-10 Hz e.g.). Span on EXA should be in the low kHz - e.g. 1 kHz. 
    
    g) Make sure IGOR delay is longer than the time taken to make a new trace. This is related to the span and the bandwidth. 
    
## 4 | Tune SQUID    

    a) Initially, tune the CURRENT BIAS. The limits of the current bias are -10 mV < I_bias < 10 mV. Sweep 0 mV to 10 mV and you should observe the SQUID turning on. It will be clear when this happens because the gainSQUID value should increase quite dramatically. It will then fluctuate but remain higher than before it turned on. 
    
    b) Look for a point on the current bias measurement where the gainSQUID value is high. Do not have it too close to the turn off point - it is better to have a slightly lower but more stable gainSQUID value at this stage. 
    
    c) Now tune the FLUX BIAS. Slowly sweep over the operating range 0 mV to 10 mV to identify areas with good gainSQUID. The full operating range of the flux bias is -10 mV < I_flux < 10 mV. Move very slowly back to the flux bias value that gives good gain. Continue to do this until you are satisfied with the gain. 
    
    d) Check the gainSQUID stability by doing a sweep over time and seeing if it stays at a satisfactory level. If it does not, there might be some problems with the SQUID. For instance, there might be a fluctuating magnetic field nearby that is affecting it. 
    
    e) Lock the DAC channels connected to the flux and current biases by setting the 'Lock' parameter to 1 (from 0) on the IGOR DAC table. 

## 5 | Switch to device

    a) Check fridge diagram to be sure of the wiring - there is a chance that it has changed since this guide was written. We now link the Zurich Instruments lock-in to the device rather than the frequency generator and signal analyser that we use to tune the SQUID. 
    
    b) Rx goes into the 'Rx' in the demodulation box. The output of the demodulation box, 'Sig Mon', goes into the Zurich input. Tx from the breakout board goes into the Zurich output. 
    
    c) Get the double dot by setting the correct voltage values for the various gates. 

## 6 | Setup ZURICH Instruments Lock-In

    a) Open the Zurich Instruments control software, "LabOne". Select 'Lock-in' and device number 4 on the size panel within the lock-in section. (The different selections allow you to run the lock-in in different software modes.)
    
    b) Oscillator goes to the correct frequency - the one that the SQUID has been tuned at and which should be in the device cavity. 
    
    c) Check the Aux output is set to the same channel that the actual device is sending to the computer. There are four channels on the front of the device - the number above the one which is directly connected to the computer is the number that should be selected here. Set the signal to demod X. Click preoffset so that the measured voltage fluctuates around ~0 V. 
    
    
## 7 | Readout 

    a) Back on IGOR. Read out I on channel 1 and VATS (voltage at the source) on channel 2. This will give both the current map and the RF map. 
    
    
    
TROUBLESHOOTING 
---------------

ISSUE: topclock(): max reached! You need to empty the root:util:wait: folder. 
SOLUTION: Delete the contents of the ./util/wait folder. Do this by entering the data browser in IGOR (Ctrl-B) and navigating to ./util/wait. Delete the contents of it - there should be 100. This is currently the maximum number before we get this warning. 
    
ISSUE: Flatline on VATS (channel 2) when making measurements after stage 7. 
SOLUTION 1: The Alazar card is saturated. Preoffset and rerun the measurement. 
    
    
