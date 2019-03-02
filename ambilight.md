---
layout: project
title:  "Ambilight"
permalink: /ambilight/
---
# Ambilight

Ambilight is the name of my custom home entertainment system. The system is a Raspberry Pi 3 B+ that runs a flask app serving various endpoints that connect to Motor, IR, NeoPixel lights behind the TV, 

**Features**

## HDMI-CEC
The Raspberry Pi is connected to my TV via an HDMI cable. This allows for the system to send out CEC codes to enable to TV to power on and off as well as the Inputs to be changed. 

## Ambi-light
In order to illuminate the neopixels behind the TV I take the signal before It hits the TV and send it to an HDMI splitter, one goes to the TV Input and the other goes through hardware HDMI to Video Composite converter, which then goes from the Composite Video out into a USB Video Converter. Which sends the signal to the Raspberry Pi via the v4l2 Video 0 device. A Python Script then uses an FFMpeg subprocess that takes the video input signal and sends it through an ffmpeg filter-chain that splits the signal into single 1xN frames, that then flip and rotate around until it follows the shape and pixel numbering of the NeoPixel strip, then the Video signal comes in as a 1x100 image Python reads the image and send the color values to the Neopixels for updating. This happens at roughly 30 frames a second. 

## HDMI Switch
A secondary HDMI switcher is used to be able to add additional inputs and split the signal to run through the Ambilight backlighting solution. This switch is controlled by an IR port. An IR blaster is connected to the Raspberry Pi via some GPIO pins, this then triggers the device to switch inputs while maintaining a single HDMI signal to the TV. 

## Volume
My entertainment system’s Volume is provided via a Bose Companion 2.1 system. The control for the volume is a round know that needs to be twisted to turn the volume up and down. To automate this I used heat-shrink tubing to make a small ring from a belt that I then connected to the knob of the Bose controller and the other end is connected to the end of a stepper motor, this motor is controlled via a DRV-8 board connected to a couple of GPIO pins allowing the motor to turn and move the volume control of the Bose.

## Apple TV Remote Pad
I wanted to add in features of Apple TV App into the Ambilight app to not have to jump between the two. I found a project called pyatv that featured a lot of the functionality that I wanted to have in the app, however it proved to be slow in use. A request would go from the iOS client when a button was tapped to the Ambilight’s running flask app and then would perform a shell script as a subprocess. This would add a second or two delay. So I did some more research for how it was able to talk to the tv and wrote a library that could communicate the TLV and was able to bring some of the Apple TV Remote scroll pad and select buttons to the Ambilight iOS app.


## iOS App
The app is a very simple one screen app that we can use at home as a controller for the system.

## Siri Shortcuts
The app ships with a handful of Siri Shortcuts that feature the ability to 

* Turn the TV on.
* Turn the volume up and down.
* Press the Apple TV Select Button.


￼


