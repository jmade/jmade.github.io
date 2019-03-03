---
layout: project
title: TransformFun!
permalink: /transformfun/
subtitle: "*A fun way to visualize 3DTransforms*"
badges: 
 - Swift-4.2-orange 
 - Xcode-10.0-blue
 - iOS-12.0-blue
 - Useful-100%25-brightgreen
 - MIT-license-brightgreen
images:
 - iphone-rotate
 - iphone-save
 - iphone-anchor
headerlink: "https://github.com/jmade/TransformFun"
---

# Transform Fun!

The inspiration for this project came from me wanting an easier way to visualize `CGAffineTransforms` rotations and translations and how the order of them affects the rendering. 

I stumbled on [this](https://www.github.com) project that featured most of this but only on an iPad and written in Objective-C. So I decided to convert some of the code into Swift and make a universal version that more suited my requirements. 

I wanted to be able to tweak animation transforms and then add them to my code, so I built in a way to share the swift code that would produce the animations and I could share it to iMessage or airdrop it directly into my Xcode project. 

I then wanted to save, edit and share the transforms so I build a document model to hold them and allow sending and receiving of the documents. 