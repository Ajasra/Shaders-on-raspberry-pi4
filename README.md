# Shaders-on-raspberry-pi4

Download the whole repo on the pi4.

Open the folder Shaders-on-raspberry-pi4 and open the file shader_on_pi4_v1.py in Geany and click run.

The code looks for the name and location of the shader... like:
shader = pi3d.Shader("shaders/paste_here")  # this runs the shader called paste_here.fs and paste_here.vs

You can paste pi4 compatible shader code in the paste_here.fs file -> must be generated by this tool:
https://github.com/louiselessel/Touchdesigner-tools [https://github.com/louiselessel/Touchdesigner-tools]


## Dependencies

Make sure to install the pi3D library or the code will not run.
Just doing the following worked on a Pi 4 w/ 1 Gb RAM. which was running the newest verision of Raspberry Pi OS (installed using the Raspberry Pi Imager (for mac) https://www.raspberrypi.org/downloads/)

Steps based on https://pi3d.github.io/html/ReadMe.html#setup-on-the-raspberry-pi.

### In terminal:

$ sudo pip3 install pi3d

$ sudo raspi-config

Then set gpu_mem=128 under -> advanced options -> memory split

The last line is to increase the GPU memory, this is default set to 64.
You want to set it higher to 128.


-------------
## ABOUT pi3d

The pi3d library comes with many other examples... I'm only focusing on shaders!

You can download the examples and have a look around for getting your bearings. 
You can also start coding right away (here is a getting started tutorial https://www.youtube.com/watch?v=gXTU6x8dQJw&feature=youtu.be)

This is how to download (Steps based on https://pi3d.github.io/html/ReadMe.html#setup-on-the-raspberry-pi):

### In terminal:

$ wget https://github.com/pi3d/pi3d_demos/archive/master.zip

$ unzip master.zip

$ rm master.zip

$ mv pi3d_demos-master pi3d_demos



To run them ALL through and test that it works, do:

$ cd ~/pi3d_demos

$ python3 RunTests.py

Otherwise just open the nameOfFile.py in Thonny and click Run.

-------------

I did not make pi3d.
Please support the community and authors over at https://pi3d.github.io/html/ReadMe.html#acknowledgements.

> pi3d is written by Tim Skillman, Paddy Gaunt, Tom Ritchford Copyright © 2012 - 2019

> Pi3d started with code based on Peter de Rivaz ‘pyopengles’ (https://github.com/peterderivaz/pyopengles) with some tweaking from Jon Macey’s code (jonmacey.blogspot.co.uk/2012/06/).

> Many Thanks, especially to Peter de Rivaz, Jon Macey, Richar Urwin, Peter Hess, David Wallin, Avishay Orpaz (avishorp), Guenter Kreidl, Benjamin Denozière, Matthew Coleman, Piotr Bednarski, @swehner and others who have contributed to pi3d - keep up the good work!
