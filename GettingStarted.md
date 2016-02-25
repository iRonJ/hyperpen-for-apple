## Starting ##

Download hyperpenDaemon.zip from the Downloads section to your computer. Unzip it by double clicking the file in the Finder. Now you should have a file named hyperpenDaemon on your disc, which should present itself as a executable unix file. Start it by double clicking and it should open in a terminal window. If the driver doesn't report **Tablet connected!** as the last line, you either haven't connected your tablet or the driver doesn't recognize your tablet. Please use HyperpenConfig for the initial setup - you'll find it in the [Downloads](http://code.google.com/p/hyperpen-for-apple/downloads/list) section.

If you want to configure the driver on your on look at ManualConfiguration.

When starting the driver shows a copyright notice and some configuration information:
```
Aiptek Tablet Driver for OSX
Designed and tested for HyperPen 12000U
(c) Udo Killermann 2012

vendor: 172f
product: 37
width: 12288
height: 6912
Offset X: 0
Offset Y: 0
screen width: -1
screen height: -1
screen Offset X: -1
screen Offset Y: -1
display ID: 1
Compensation: 0
Average: 2
Pressure level: 1
Physical max level: 1023
Screen Boundary: 1920.00, 0.00 - 1280.00, 800.00
Screen Mapping: 0.00, 0.00 - 1280.00, 800.00
Tablet connected!
```

The last line is only shown if you already have your tablet connected to your computer. Otherwise it will show as soon as you plug your tablet into the USB port and the green light on the lower right starts to blink.

That's it - just switch to the drawing application of your choice and start your artwork. If you select the right tool (i.e. a pressure sensitive one) you'll notice that the stylus now works in a different way. The line width will depend on the pressure you apply to the stlylus. The position of the mouse pointer relates directly to the position of the stylus on the tablet.

My driver enables the soft buttons on top of the tablet and executes the commands printed on them. So you can cut, copy, paste and so forth as you'd expect from the imprint. You can even start Excel, Word, Mail and Safari by clicking on the soft buttons. Excel and Word will only start if you have installed them on your computer.