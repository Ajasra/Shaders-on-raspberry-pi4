# Shaders-on-raspberry-pi4

This repo allows you to run shaders on a Raspberry pi 4, using the pi3d library. 
It enables you to use code from https://www.shadertoy.com/ and try it on the pi4.

Examples:

- Ex_Simple runs a shader from Shadertoy at the resolution you specify. If fullscreen, the shader will be the resolution of your screen.
- Ex_Downscale runs a shader from Shadertoy at the resolution you specify, but scaled (SCALE) down for better performance on the pi. Also if fullscreen.
- Other examples use postprocessing to render effects based on the Shadertoy shader. Here the shadertoy shader is treated as a buffer for sampling from.


![Downscale example 0.8](https://github.com/louiselessel/Shaders-on-raspberry-pi4/blob/master/Work-in-progress/Documentation/Screenshot_0.8scale.png)
![Downscale example 0.2](https://github.com/louiselessel/Shaders-on-raspberry-pi4/blob/master/Work-in-progress/Documentation/Screenshot_0.2scale.png)
![Postprocessing example](https://github.com/louiselessel/Shaders-on-raspberry-pi4/blob/master/Work-in-progress/Documentation/Screenshot_postprocessing.png)


## HOW TO

Download this whole repo on the pi4.
  
Open the folder Shaders-on-raspberry-pi4 and open any of the examples in the Ex_name folders.
  
Open the .py file (run_shader_w_downscale.py) in Geany and click run.


The code looks for the name and location of the shader... like:
	
	shader = pi3d.Shader("shaders/nameofshader")  # this runs the shader called nameofshader.fs and nameofshader.vs in shaders folder
	
	shader = pi3d.Shader("nameofshader")  # this runs the shader called nameofshader.fs and nameofshader.vs
		
	flatsh = pi3d.Shader("post_vanilla")  # this post processing shader samples the shadertoy shader and makes the downscaling work. Don't change it.
	postsh = pi3d.Shader("post_Pixelize")  # this post processing shader generates pixelation. You can make other postprocessing shaders like this one.


You can paste pi4 compatible shader code from shadertoy in the nameofshader.fs file -> can be auto-generated by this tool

https://github.com/louiselessel/Touchdesigner-tools [https://github.com/louiselessel/Touchdesigner-tools]

Remember to credit the original creator on shadertoy!


NOTE: 
Currently only fragment shaders (.fs files) are implemented.
You can delete the work-in-progress folder. I use that for experiments, they are not guaranteed to work.

Thank you to Paddy Gaunt (@paddywwoof) for excellent help and advice on implementing this.


## Dependencies

Make sure to install the pi3D library, or the code in this repo will not run.
Just doing the following in the terminal worked on a Pi 4 w/ 1 Gb RAM. which was running the newest verision of Raspberry Pi OS.
The Pi OS was installed using the Raspberry Pi Imager (for mac) https://www.raspberrypi.org/downloads/.

The following steps are based on https://pi3d.github.io/html/ReadMe.html#setup-on-the-raspberry-pi.

### In terminal:

	$ sudo pip3 install pi3d

	$ sudo raspi-config

Then set gpu_mem=128 under -> advanced options -> memory split

The last line is to increase the GPU memory, this is default set to 64.
You want to set it higher, to 128.


-------------
## ABOUT pi3d

The pi3d library comes with many other demo examples... I'm only focusing on shaders!

You can download all of the other demos, but it is not necessary for running my shader examples. 
You can also start coding pi3d right away (here is a getting started tutorial https://www.youtube.com/watch?v=gXTU6x8dQJw&feature=youtu.be)

This is how to download the demos (Steps based on https://pi3d.github.io/html/ReadMe.html#setup-on-the-raspberry-pi):

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
