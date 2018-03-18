
8 Bits CPU
Another faster 8 Bit machine, with a much bigger screen and a Hex kb for I/O.
The big new thing is the Hard Drive and with it a lot of software!

Gone are the days of loading the ram image of a single program before running it.
Now the CPU boots itself, the MBL gets the ram ready and then a prompt appear on screen, ready for a command line!

The OS is very primitive, basically a library of functions in Ram 900h:
900 _loadOsFunction(r3)
930 _getchar() --> r6
940 _putchar(r3)
a50 _getline() --> Kb Buffer [c42]-[c5f]
ac0 _printString(r4,r5)
0f2 _exec(r3) 
b80 _printBiteDec(r3)
bb6 _printBiteHex(r3) 

The Hard drive immage contains a number of programms:

5 MBL Master Boot Loader, It's called by default when booting the CPU, loads a ram image with the OS and runs CMD.
7 CMD It's a simple DOS like console that displays a prompt and waits for commands, just type the inode number of the program you want to run from this list.
8 DIR It a clone of the dir command in dos (list) that lists the content of the root directory (2) by default or the specified directory if you provide a parameter >8 3 for Sys.dir or >8 10 for test.dir
9 Fib It's a recursive implementation of Fibonacci to test stack discipline, it asks for an input, n, and prints Fib(n)
11 Sum1000 Sums the first 1000 integers and prints out the result in hex
12 Nprime  Finds the first 4 prime numbers
13 IO Test Prints a menu, asks to choose an option and prints out theascii table, a picture or a echo of the input line
14 Hex Editor It's a very basic editor, you can load blocks in ram from HD, prints a page of ram to screen, write or modify a page in ram and then save it in HD.

To run the simulation:
open logisim
open the 8.4.2 Boot from HD.circ file
find the HD chip on the far right of the CPU
right click and "load image" of any of the "HD images" files

In logisim "Simulate" menu, select "Ticks enable" and a frequency.
In the top left of the circuit click the "Boot from HD" button and give it a moment to load the OS then you should see
the Header on screen and then the imput prompt, ready for a command. you can type on the Hex Keyboard in ascii (38 hex for '8')
followed by return (0d hex).

