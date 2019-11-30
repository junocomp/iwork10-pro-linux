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


<b>Installation</b>

Download and install Ubuntu 19.10

Update all packages

Install extra drivers drivers

sudo apt install intel-opencl-icd preload intel-media-va-driver-non-free linux-tools-generic

Copy 20-intel.conf to /usr/share/X11/xorg.conf.d/ this will help accelerate the Intel Graphics

