## Calibration ##

Some of you have asked for a way to calibrate the driver. I understand that this is important for display/tablet combinations such as Yiynova MSP 19 when the video signal is transmitted via VGA. From the beginning the driver has the options -x and -y to manually adjust the upper left point the tablet recognizes as (0,0). You need to fine tune the driver by playing around with these parameters. I will come up with a better way once I have some time for a GUI. Look at ManualConfiguration for details.

## Macro keys ##

I used the standard layout of Hyperpen 12000U and programmed the driver to support this layout. So you have cut/copy/paste, can start Word and Excel and launch your favorite internet browser. There is a feature hidden in the driver so you can override these layouts application wise. Again I will make this available when I have implemented the appropriate user interface.

Some information for the experienced user is available: BehindTheScene.

## Latest updates/features ##

**Update (08/31/2012)**: Improved hyperpenConfig to support additional options built into the driver. Now you can set the pressure levels of your stylus, the display you want to control with the tablet, and the number of samples used to average.

**Update (04/27/2012)**: Added option -a to average stylus' postion over some samples. This reduces the level of jitter and smoothes the lines you are drawing. On the other hand the hyperpenConfig utility now works with Lion and doesn't grey out the save button anymore.

**Update (03/04/2012)**: Added standard configurations for Hyperpen Mini and 12000U in the download section. Just copy these into the same directory your hyperpenDaemon resides. You decide if you want to go with 4:3, 16:9 or 16:10 by starting the corresponding .command file.

**Update (02/26/2012)**: Added a configuration utility. The dialog helps you to select the right options and configures the driver appropriately. Please look at HyperpenConfig for details.

**Update (02/12/2012)**: Fixed an issue of jumpy pressure values. Leading from strong to very thin lines almost immediately. Now it's smooth as you'd expect it.

**Update (02/12/2012)**: Now you have a way to compensate mechanical restrictions of your pen. Using option -c you can now specify the pressure value the system sees as 0. In the commercial driver this feature is named _calibration_. But it doesn't calibrate anything. Instead it helps to find the right compensation value and stores it internally.

**Update (11/30/2011)**: I have bought a Hyperpen Mini (aka Trust Flex Design Tablet, Waltop Q Pad) tablet to test the driver with another Aiptek tablet. If configured properly the driver works for this tablet as well. If you want to use it in 16:9 go with `-v 0x172f -p 0x37 -w 12288 -h 6912`. If you want to stay with 4:3 use `-v 0x172f -p 0x37 -w 12288 -h 9216`.

**Update (12/24/2011)**: There is one issue with some stylus' which are mechanically restricted. It seems some of them don't relax to 0 if released from the tablet. The stylus of my Mini tablet only relaxes to a pressure around 32. I'll add a command line option to calibrate this offset.

## Motivation ##
The driver delivered by Aiptek isn't suited for current versions of OSX. It took me so much time to look for a recent one (never actually found it) so I decided to do it on my own.

I developed and tested the driver for Hyperpen 12000U and Hyperpen Mini. Users have reported it works with **Trust** and **Medion** tablets as well. As these are rebranded **Waltop** tablets, the driver should work with the original as well.

I hope others will like it and suggest code improvements and extensions.
```
Please send me some feedback! Does the driver work for you as expected? What issues came up? What is missing?
udo dot killermann at gmail dot com
```

## Short Overview ##

It has to be started from the command line (or by double clicking in the finder - look GettingStarted). It supports drawing with the stylus and recognizes pressure as well as the side switches. It has plug and play detection of the tablet to set up and shut down the event pump which processes the tablet's reports. Start the daemon and change to the drawing application you want to work with.

If you came looking for code snippets: The code gives you an idea how to work with **IOHIDManager** and USB plug'n play. You need to have basic knowledge of Core Foundation and its features to get a start.


## Credits ##

I reused code from [Tablet Magic](http://www.thinkyhead.com/tabletmagic) to get my effort started. The available commands and the way tablet status info is to be interpreted I got from the Linux Kernel driver's [documentation](http://lxr.free-electrons.com/source/drivers/input/tablet/aiptek.c). So I am thankful the authors contributed their work as open source under an open license.

My code is open and free for others to reuse.

Please let me know if the driver works for you (udo dot killermann at gmail dot com). I have only one tablet at hand and one Mac to hook it to. So my setup isn't suited for a field test.

I have trained and tested the driver with demo applications available at [Wacom's](http://www.wacomeng.com/mac/index.html) developer site.