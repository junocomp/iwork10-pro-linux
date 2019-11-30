<b>Ubuntu drivers for iWork10 Pro</b>

Tested on Ubuntu 19.10

<p><b>Works</b><br>
ꔷScreen rotation (somewhat)<br>
ꔷIntel graphics acceleration<br>
ꔷScaling<br>
ꔷAudio<br>
ꔷWifi</p>

<p><b>Doesn't work</b><br>
ꔷTouchscreen (not calibrated)<br>
ꔷFront and back camera<br>
ꔷThunderbolt 3 video output</p>


<b>INSTALLATION</b>

Download and install Ubuntu 19.10

Update all packages

<b>Install extra drivers drivers</b>

`sudo apt install intel-opencl-icd preload intel-media-va-driver-non-free linux-tools-generic`

Copy `20-intel.conf` to `/usr/share/X11/xorg.conf.d/` this will help accelerate the Intel Graphics

Copy `rotate-screen` to `/usr/bin/`

`sudo chmod 755 /usr/bin/rotate-screen`

Then execute 

`rotate-screen&`

`exit`

This should give you full screen rotation. So far I have not figured out how to add it at startup. Maybe I need to create a systemd service.
