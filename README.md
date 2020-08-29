# Bangood-N76E003AT20-51-Development-Board
OLED driver and test for the Bangood N76E003AT20 51 Development Board (Nuvoton 8051 family processor)

This is a work in progress project to port a SPI OLED graphics library to this development board. The code is ported from code written for Keil to the sdcc compilier.

Currentally the code is rough around the edges and not all of the OLED graphics driver has been ported to sdcc. But it works well enough to test the OLED display on the development board.

It so far works (compiles and uploads) from my Mac. Using cmake so it may be possible to port the build scrips to Windows.

THe programmer used to program the development board is a generic clone Nu-Link programmer avaliable on eBay and elseware. The program to operate the programmer is avaliable here: 
https://github.com/mountaintom/nuvoprog

As this code is still in a rough state, and untested on any other computer than my Mac, it may be necessary to adjust something in the shell scripts or CMakeLists.txt file.

However the steps to build, upload and test the code is as follows:
1) Run the shell script: ./project-build.sh 
   The cmake build will be run and everything built. 
2) Run the shell script: ./programmer-chip-program.sh 
   The newly built 8051 (Nuvoton MS51FB9AE or N76E003) code will be uploaded to the development board.
   
The build will automaticly build the main C file, find, build and link the dependencies. Just put your main C file in the prj-main directory and any libraries in prj-componets. The build scrips will do the rest and place the output in the prj-build directory. Whatever you call your main C file, the compiled output files will have the same name. 
