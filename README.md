Ubuntu drivers for iWork10 Pro
------------------------------

Tested on Ubuntu 19.10

<p><b>Works</b><br>
ꔷScreen rotation (somewhat)<br>
ꔷIntel graphics acceleration<br>
ꔷScaling<br>
ꔷAudio<br>
ꔷWifi</p>

<p><b>Does not work</b><br>
ꔷTouchscreen (not calibrated)<br>
ꔷFront and back camera<br>
ꔷThunderbolt 3 video output</p>


INSTALLATION
-------------

Download and install Ubuntu 19.10

Update all packages

<b>Install extra drivers drivers</b>

`sudo apt install intel-opencl-icd preload intel-media-va-driver-non-free linux-tools-generic`

Copy `20-intel.conf` to `/usr/share/X11/xorg.conf.d/` this will help accelerate the Intel Graphics

Copy `rotate-screen` to `/usr/bin/`

`sudo chmod 755 /usr/bin/rotate-screen`

Then execute 

`rotate-screen&`<br>
`exit`

This should give you full screen rotation. So far I have not figured out how to add it at startup. Maybe I need to create a systemd service.

<b>Enable HiDPI Fractional Scaling fox x11 and Wayland</b>

X11<br>
`gsettings set org.gnome.mutter experimental-features "['scale-monitor-framebuffer']"`

Wayland<br>
`gsettings set org.gnome.mutter experimental-features "['x11-randr-fractional-scaling']"`

<b>GRUB</b>
Add `acpi_osi='Windows 2015' acpi_backlight=vendor video=efifb fbcon=rotate:1` to `GRUB_CMDLINE_LINUX_DEFAULT`

`GRUB_CMDLINE_LINUX_DEFAULT="quiet splash acpi_osi='Windows 2015' acpi_backlight=vendor video=efifb fbcon=rotate:1"`


Touchscreen
-----------

I have extracted SileadTouch.sys from Windows 10, which is the touch driver. There is a tutorial on how to port this to linux using <a href="https://github.com/onitake/gsl-firmware">gsl-firmware</a> and <a href="https://github.com/onitake/gslx680-acpi">gslx680-acpi</a>. I was able to convert and install the driver but it needs to be calibrate and I have not been very success doing it. If anyone knows how to do it, please open an issue and describe how to.
