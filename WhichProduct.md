## How to get vendor and product id for your tablet ##

If you aren't into development but need to know which values to fill into the vendor and product information needed by the driver: have a look into the apple menu. Follow "About this Mac" and choose "More information..." in the dialog showing up.

This way you start the _system profiler_ which gives you a lot of system insights you don't really want to know about ;-)

In the hardware section in the left pane go down to "USB" and the system shows you the devices which are connected via USB to your Mac. Now look for an entry that has something with "tablet" in it and select this entry.

The details tell you product id and vendor id as well. On my system vendor id is 0x08ca and product id is 0x0010.

![http://hyperpen-for-apple.googlecode.com/svn/wiki/system%20profiler.jpg](http://hyperpen-for-apple.googlecode.com/svn/wiki/system%20profiler.jpg)