This contains the working of 7 segment display with the help of 7447 BCD / IC
# 7447
### What is 7447 ??
The 7447 is a BCD-to-Seven-Segment Decoder/Driver integrated circuit (IC). BCD stands for Binary-Coded Decimal, which is a way of representing decimal numbers using four binary bits. The 7447 IC takes a BCD input and converts it into the 7-segment display format.
### Key features of the 7447 IC include::
<pre>
  <b>1)BCD Input:</b> It accepts a 4-bit Binary-Coded Decimal (BCD) input, representing decimal digits 0 through 9.

  <b>2)7-Segment Output:</b>The 7447 converts the BCD input into the corresponding signals for a 7-segment display. A 7-segment display is a visual representation of numbers using seven individual segments, labeled A through G, arranged in the shape of the number "8."

  <b>3)Decimal Point Output:</b> Some versions of the 7447 also include a decimal point output for displaying decimal numbers.

  <b>4)Latch and Lamp Test Inputs: </b>The 7447 may have additional inputs for latching the current input and for testing the display lamps.
</pre>
### But Why 7447 ? When we can directly display numbers using arduino 
Yes displaying numbers on 7 segment display is also possible directly without any intervention of 7447, but the process here is lengthy and we need to provide it with the binary number format, which is quite hectic. 
### So.. To Solve this:
We use 7447 Decoder in order to take digital numbers as input and generate a format that is then sent to 7-segment display in order to simplify our work.<br>
i.e we use arduino to send info to 7447 which in turn converts it and sends to 7-segment display.
