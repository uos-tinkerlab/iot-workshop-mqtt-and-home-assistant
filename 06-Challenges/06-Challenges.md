# 06 Challenges

Well done for getting this far! Have a go at one of our challenge tasks that builds on what you learnt or try one of our other workshops. Whatever takes your fancy. Enjoy :)

## Challenge tasks
1. Instead of using a LDR to dim the lights, can you make the light dim when you turn a variable resistor, like a dimmer switch. If your new to potentiometers, this might help https://www.halvorsen.blog/documents/technology/iot/pico/pico_potentiometer.php

2. Can you make traffic lights? Give one of the Pi Pico's a push button and replace the red LEDs with one red, yellow and green on  the other. Have a look at the light sequence:
https://theorytest.org.uk/wp-content/uploads/2019/03/traffic-lights-sequence.jpg

3. Can you make a morse code communication device? Give one of the Pi Pico's a push button and make the LEDs light up on the other Pi Pico in sync with the push  button. Could you make this bi directional.

4. Can you send commands between the Pi Picos? Instead of only sending numbers, try sending words such as `on`, `off`, or `flash` using MQTT. Change the receiving Pi Pico's code such that it performs a different action with the LED depending on the received message.

5. Can you make the Pi Picos communicate both ways? So far, one Pico has been the sender and the other has been the receiver. Can you make both Pi Picos publish and subscribe to MQTT topics? For example, one Pico could send a message to the other, and the other could respond with an acknowledgement.
  - For an extra challenge, compare this with challenge 4 to have both Pi Picos control the other

6. Can you connect more than two devices? MQTT does not limit you to one sender and one receiver. Join up with another group and try connecting three or more Picos to the same MQTT topic. Can you make one LDR control the others?


## Other workshops
 - Use the Pi Pico  Inventor board and learn how to control RGB Leds: https://github.com/uos-tinkerlab/Pi-Pico-Inventor-RGB-LEDs
 - Want to do more breadboarding and want to try coding in Arduino IDE? Try this workshop: https://github.com/uos-tinkerlab/eee-workshop#