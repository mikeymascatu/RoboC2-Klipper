# RoboC2-Klipper

Watch these videos for context:
https://youtu.be/PIkeEP66ZNs - Part 1
https://youtu.be/5eVwbW5pNZ0 - Part 2

So here's my version of a printer.cfg file for a Robo3D C2 in 2024.

Performance stats:
300mm/s MAX (I tested 200)
3k Accel

Requirements:
Robo C2
SD Card (16+ Gb)
Internet

*OS Installation*

Flash MainsailOS (32 Bit) onto a SD card

Follow this guide:
https://help.robo3d.com/hc/en-us/articles/115001580151-Replacing-your-MicroSD

Power on the printer and log into the Pi via ssh

*Touchscreen Drivers*

Enter these commands (seperately)

git clone https://github.com/waveshare/LCD-show.git
cd LCD-show/
chmod +x LCD35-show
 ./LCD35-show

 Restart the Pi

Klipper install*

Install KIAUH to make things easier
https://github.com/dw-0/kiauh

Flash MCU firmware, there are many videos on how to do this so I won't explain.
Target: ATmega 2560 with no additional settings

