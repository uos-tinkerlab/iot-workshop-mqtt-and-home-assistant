# 02 Flashing LEDs

The Pi Pico Inventor board has 12 RGB LEDs to be controlled,



## Creating and saving a program
1. First you need to create a new python file. 
Go to the top "file"➡️"new".  
Then go "file"➡️"Save as..."➡️"This computer". Choose somewhere in your U drive to save it with a name like "LedFlash.py".

## Controlling the LEDs

1. Type in the following code and click the green play button in the top left to run it:

    ```python
    from inventor import Inventor
    board = Inventor()

    board.leds.set_rgb(0, 255, 255, 255)
    ```

    This creates an object called `board`, that lets us set the first LED (`0`), to produce as much red,  green and blue as possible (`255, 255, 255`) creating white light.

2. Try running this code instead:

    ```python
    from inventor import Inventor
    board = Inventor()

    for i in range (0, 11):
        board.leds.set_rgb(i, 255, 255, 255)
    ```

    Everything indented below the `for` will loop 12 times. On each loop the value of `i` is incremented from 0, to 11. This means that the LED corresponding to `i` is set to white

3. Try this code:
    ```python
    from inventor import Inventor
    import random
    import time
    board = Inventor()

    #Brightness of the different LEDs
    red = 0
    green = 0
    blue = 0

    while True:#Loops forever
        time.sleep(1) #waits one second
        
        #Generates a random values from 0 to 255
        red = random.randint(0, 255)
        green = random.randint(0, 255)
        blue = random.randint(0, 255)
        
        #Sets the brighness of red, green and blue
        for i in range (0, 11):
            board.leds.set_rgb(i, red, green, blue)
    ```
    The code now chooses a random numbers for the brightness of red, green and blue each second.

## Challenges
Feel free to have a mess around with the code or try one of the challenges:
- Can you make it flash Red 3 times when the "user" button is pressed?  
**Hint:** Use `state = board.switch_pressed()`. State will either be `True` or `False`.
- Can you make it pulsate colour, smoothly transitioning from them being fully off to fully on?  
**Hint:** To make it wait in milliseconds use `time.sleep_ms(100)`.

