---
layout: project
title: PixelBox
permalink: /pixelbox/
subtitle: "*Virtual Light-Bright with Physical display*"

badges: 
 - Swift-4.2-orange
 - Xcode-10.0-blue
 - iOS-12.0+-blue
 - MIT-license-brightgreen

images:
 - iphone-main
 - iphone-other
headerlink: "https://github.com/jmade/PixelBox-iOS"
---
# PixelBox

Pixel Box is a 16x16 grid of NeoPixels connected to a Raspberry Pi Zero W running a flask server that allowed an iOS app to update the pixels with different colors. 

## Pixel Rain
This feature added random generation of pixels lighting up quickly from the top of the grid to the bottom to emulate rain. You could also add in custom rain drops 

This feature utilizes a linux named pipe to tell a background Python Process to run and also receive the new raindrop placements while the main flask loop also ran and served the site.

## iOS App
This app featured one main view with a tab bar allowing the user to switch from the main grid interface to viewing and loading saved creations. 

## Color Picker
utilized a UIPopoverView to contain a ColorWheel to select the color from, and a history or colors chosen

## Document Saving
You can save the creations as .pixel files using a small DocumentSaving library that serializes the pixel location and color data along with a snapshot image of the grid.