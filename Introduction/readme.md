

# Blink Program (LED Blinking using Arduino)
The Blink program is the simplest way to understand how Arduino controls digital outputs. It turns an LED ON and OFF at regular intervals.

How It Works?
The Arduino sends a HIGH or LOW signal to an LED.
The delay() function controls how long the LED stays ON or OFF.
A digital pin (e.g., pin 13) is assigned to control the LED.

# 7-Segment Display Using Arduino
A 7-segment display is used to show numeric values (0-9) by controlling seven LED segments manually. 

How It Works?
A common cathode 7-segment display is used, where all segment grounds (GND) are connected together.
Each segment (A-G) is connected to Arduino digital pins.
By sending HIGH or LOW signals, numbers are manually displayed.
Pin Mapping (Common Cathode 7-Segment Display)
Segment	Arduino Pin
A	          2
B          	3
C          	4
D	          5
E	          6
F          	7
G	          8
