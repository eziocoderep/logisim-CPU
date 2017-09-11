
8 Bits CPU
A faster 8 Bit machine, the ram is a bit more elaborate with a separate circuit to test caches.
There is a small led screen and a simple input kp to test I/O

The instruction set has been expanded.
It comes with 2 test progam written in the cpu asm:
-Sum1000 sums the first 1000 integers and saves the result in memory
-Nprime finds the first 4 prime numbers

To run the simulation:
open logisim
open the .circ file
find the ram chip in the loader at the center of the CPU
right click and "load image" of Nprime or Sum1000

In logisim "Simulate" menu, select "Ticks enable" and a frequency.
In the top left of the circuit click the "loader 256" button or the 4k version
(the ram is split in 2 chips so the code needs to be loaded in ram by the cpu before you can run it)
(this is a pain and will ideally be sorted by a file system and a hard drive chip somewhere in the future)
when loader has finished click the "ON" light green button.

The 8.3.x directory contains various components tests:
- DMA a direct memory access to connect a HD to the next cpu I'm planning the 8.4.x
- MMU a memory management unit to implement virtual memory and in theory processes
  It's a bit of a dead end, the hardware for VM works fine but this machine address space
     is way to small for the necessary code (scheduler process tables etc)
- More I/O test devices: a new led matrix screen and a Hex keyboard with the supporting hardware

