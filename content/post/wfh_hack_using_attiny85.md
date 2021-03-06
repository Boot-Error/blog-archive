+++
type = "post"
title = "WFH Hack with Attiny85"
description = ""
published = "25-03-2021"
tags = ["arduino", "usb", "automation"]
+++

I'm restricted to using my Work Laptop for everything related to work and it's all great and usual, but with a minor inconvenience.
The laptop hibernates after couple of minutes of inactivity, and If walk away for a coffee, I'll miss on important notification, delaying my response.

And I can't change the screensaver settings, which is acceptable. Hence, I came up with this hack.

<!-- more -->

### My Smart friend's hack

A friend of mine came up with a simple hack, where he would place his Analog Watch underneath the mouse's optical sensor. The movement of the second hand would constantly trigger some mouse activity which stops his laptop from hibernating.

This is great, but I felt it too tedious and I didn't have a watch (duh I got my smartphone to check time). I needed a better solution.

## Meet Attiny85

Attiny85 is an Atmega Series microcontroller and the package above is size of a thumb with a PCB craved out like a USB port. I can write Arduino code which can run on this tiny microcontroller. This includes writing a programmable USB HID 😈

![Attiny 85](/post/images/digispark_attiny85.jpg)

I had one lying around, time to build one.

## The Mouse Jiggler

To trick my laptop into thinking I'm using it, the Attiny 85 program does the following in bare minimum

- For Every 2 minutes,
	- move the mouse pointer to any direction
	- move the mouse pointer back to where it was

For the computer, this is a mouse activity meaning the user is active. The computer would reset its screen saver timeout.

Follow instructions [here](https://www.instructables.com/Digispark-Attiny-85-With-Arduino-IDE/) to setup Arduino IDE for programming this board 

Here is the code, the phantom user to my computer!

{{< gist Boot-Error 394b2102a1a23b8baf0bc80c18ebe898 >}}

Compile and upload the sketch and watch your computer tricked into thinking you are always working! 

This Mouse Jiggler won't even interrupt while you are working since it's actions are so swift, unless you do a lot of art using mouse then prepare for some erroneous lines in your drawings.
