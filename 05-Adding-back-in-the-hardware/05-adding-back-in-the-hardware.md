# Adding Back in the Hardware

In this exercise you will be building a remote light switch. One Pi Pico will have a light sensor (LDR) on it and, it will send data to the other Pi Pico which will use  PWM to dim itself accordingly to the  light levels.

## How do we use a LDR?
A light dependent resistor changes how much resistance it has based on the amount on light hitting it. 

We can connect it in series with a resistor, between ground and voltage. Some of the voltage gets lost in the resistor and some in the LDR. when  the resistance of the LDR changes, a different amount voltage gets lost across the LDR. This is called a voltage divider.

We can measure this voltage lost across the LDR by connecting it to one of the Pi Pico's pins. The voltage measured will change when the LDR's resistance changes, therefore it changes when the light intensity changes.


## Adjusting the  sending Pi Pico's breadboard
The Pi Pico with the code that sends the messages needs to have a LDR and Resistor added to its breadboard. Work on this still in your pair.

You will need the following components:
- 1x LDR
- 1x 4k7R resistor (may be a blue colour instead of brown)
- 2x jumper wire. Have a look at the pictures to get the right lengths.  

![alt text](PXL_20260928_161654204.jpg)  


1. First unplug the Pi Pico
2. Connect one of the legs on the LDR to 3.3V via a breadboard wire, as shown in the picture
![alt text](PXL_20260928_161444631.jpg)
3. Use a a bread board wire to connect the other leg the pin on the Pico shown in the picture. Also connect the other leg to ground via the 4k7R resistor
![alt text](PXL_20260928_161412252.jpg)
4. After you have check your  connections replug your Pi Pico
4. Press the stop button at near top of Thonny for it to to be recognized again.

## The sending Pi Pico

As a pair you need to adjust the code. So that data about the amount of light is sent in the messages.

By using `ldr.read_u16()` we can get a 16 bit value back for the voltage on that pin. Meaning if the pin measures 3.3V it returns 65, 535 for 3.3 volts and if it measures 0V it returns 0.  

**Replace your entire `while True` loop in the sending Pi Pico's code with the following:**
  
```python
# Setup ADC on GP28 to read that pins voltage
ldr = machine.ADC(28)

#Loops forever
while True:
    voltageMeasurement = ldr.read_u16(); #reads the voltage
    print(voltageMeasurement)
    client.publish(publishTopic, voltageMeasurement) #publishes the voltage reading
    
    time.sleep(2) #Loop every 2 seconds
```

## The receiving Pi Pico

We need to change the code on the receiving Pi Pico so that it uses PWM  to adjust the  brightness of its LEDs based on the message sent by the sending Pi Pico.






