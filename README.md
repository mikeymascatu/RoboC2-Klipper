# Klipper on the Robo3D C2
## Tools for running Klipper (MainSailOS) on the Robo C2

## Watch these videos for additional info.
https://youtu.be/PIkeEP66ZNs - Part 1
https://youtu.be/5eVwbW5pNZ0 - Part 2

## Introduction

The Robo3D C2 was a Mid-Tier 3D printer from November 2016 made by the silicon valley start-up, ROBO3D.

This printer was targeted as an "Out of the Box" 3D printer. Basically the Bambu Lab of 2016 (Hi Speed, Touchecreen, Usability, multicolor, ect)
Retailing at $699, the C2 was overshadowed in features to the R2, the larger, enclosed variant of the C2.

The C2 runs on a modified version of Octoprint and Marlin 1.1. The MCU architerture is the ATmega2560 (Ardunio Mega) and the host featured a RPi 3B. Both are usable with Klipper.

The C2 kinematics were designed for speed with an advertised travel speed of 250mm/s at 3k velocity. However, the outdated software and cooling handicapped the C2 at around 50-90 mm/s printing speed. With a goal of OSW (Open-Source Software) and 3D printing being sustainsblity and repairability, my goal is to reduce the waste of an aging platform by making this ancient printer competitive with today's printers. 

This conversion can be done with no external modifications. No additional parts other than a seperate SD card (highly recommended). Experience working with Klipper is recommended but not required and serves as a moderately difficult project depending on the experience.   

So here's my version of a config file for a Robo3D C2 in 2024.

## Atribution and other guidelines:

You're free to do anything with this config as per Klipper's open-source guidelines. I would appreiate atrribution as "mikeymascatu" or "PRINT IT PERFECT" but isn't required. This was tested on only my C2 so your milage may heavily vary.

## Working Additional Features:

Ethernet and Wifi

Full KlipperScreen

Cooling Fan Control 

Pausing

Filament Runout and Detection

Direct intergration with MainSail compatible slicers (OrcaSlicer)

Auto Bed Leveling

## Broken or in-progress Features:

Optimized OrcaSlicer Profiles

Speed Tuning

G-code Macros for Loading and Unloading (Loading/Unloading manually does work currently)

Tested Slicers: OrcaSlicer

## Physical Requirements:

Robo C2

SD Card (16+ Gb)

Internet

## Recommended Skills:

Some moderate knowledge of the behind the scenes of 3D printing (like working on an Ender)

Moderate-High level Computer Knowledge (if you're tryng this, you're probaly good enough)

Basic knowledge of the Linux CLI

### NOTE:
The Robo R2 has very similar architechure to the C2, but there are some things that are different. Bed Size, Heating, Lighting Control, Touchscreen, ect.
Feel free to edit and add a R2 config, but they are different enough where REALLY BAD THINGS can happen so TEST AT YOUR OWN RISK.

### *OS Installation*

Flash MainsailOS (32 Bit) onto a SD card using RPI Imaging Tool

Follow this [guide:](https://help.robo3d.com/hc/en-us/articles/115001580151-Replacing-your-MicroSD)

Power on the printer and log into the Pi via ssh

### *Touchscreen Drivers*

Enter these commands (seperately)

```
git clone https://github.com/waveshare/LCD-show.git
cd LCD-show/
chmod +x LCD35-show
 ./LCD35-show
 ```

 Restart the Pi

### *Klipper install*

Install [KIAUH](https://github.com/dw-0/kiauh) to make things easier

Flash MCU firmware, there are many videos on how to do this so I won't explain.
Target: ATmega 2560 with no additional settings

### *RPI MCU Config*
[This allows filament runout to work:](https://www.klipper3d.org/RPi_microcontroller.html?h=host)

### *Config*
enter mailsailos.local into any web browser

Download the printer.cfg and upload it into MailSail

Uncomment the comands with CUSTOMIZE BEFORE USING above them. Set the values to what you need.

### *Install Klipperscreen*
Use KIAUH again to install KlipperScreen.

[Set your Probe Offset:](https://www.klipper3d.org/Probe_Calibrate.html)

Make sure you [Calibrate Mesh](https://www.klipper3d.org/Bed_Mesh.html?h=mesh#adaptive-meshes) and [Pressure Advance](https://www.klipper3d.org/Pressure_Advance.html?h=press)

That should be everything that's specific to the Robo C2

# Optional: Robo C2 Cooling Mod:
This is an offical mod made by Robo3D and comes in handy when printing at those speeds:
[Offical Guide](https://help.robo3d.com/hc/en-us/articles/360001909492-Precision-Air-Flow-Fan-mount-printed-add-on) and 
[STL](https://www.thingiverse.com/thing:2833645)

# OrcaSlicer

I uploaded my configs from OrcaSlicer so people have a headstart.

## Installation

In OrcaSlicer, Go to File>Import>Import Configs and select this file
