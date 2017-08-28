
4 Bits CPU
This is a proof of concept done in NAND Gates, exept for the ram chip.
(There are 16 bits of Ram built in Nand but that whole ram in nand would be just too heavy)

The instruction set is very limited and the whole thing rather slow.
It comes with 2 test progamm written in the cpu asm:
-Sum1000 sums the first 1000 integers and saves the result in memory
-Nprime finds the first 4 prime numbers

To run the simulation:
open logisim
open the .circ file 4.0.1...
find the ram chip on the far right, on the memory bus
right click and load image of Nprime or Sum1000

In logisim "Simulate" menu, select "Ticks enable" and a frequency.
In the top left of the circuit click the "ON" light green button.
(you may have to hold it for a bit if you select a very slow frequecy like 1Hz)

