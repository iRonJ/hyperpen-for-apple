# Pressure Profiles #

## Sneak Preview ##
**Disclaimer: This feature will be posted to the Downloads section soon. Then I will remove this disclaimer.**

Normally the pressure you impose on the pen is reported as such to the system. If your pen supports 512 pressure levels, then 0 will be reported as 0 and 511 as 1 to the system. So 255 is 0.5 and so on. This behavior is standard and most of the time expected. But what do you do if you need another behavior, one that allows you to simulate a hard or a soft pen for example? You can either purchase a professional application (e.g. Photoshop) that allows you to define pressure profiles or you can rely on my driver to do this for simpler applications as well.

To define the pressure profiles I have developed a utility that does just that. It's name is `pressureProfile` and you start it by double clicking in the finder.

It will come up with a window like this:

![http://hyperpen-for-apple.googlecode.com/svn/wiki/pressureProfiles/linear-20121001.jpg](http://hyperpen-for-apple.googlecode.com/svn/wiki/pressureProfiles/linear-20121001.jpg)

The first pressure profile is always the linear one, it just mimics the standard behavior of physical pressure input and logical pressure reported by the driver.

You can define your own profiles by clicking `[+]` and remove a defined profile by clicking `[-].

I'll show you two of my definitions that simulate hard and soft pens:

![http://hyperpen-for-apple.googlecode.com/svn/wiki/pressureProfiles/hard-20121001.jpg](http://hyperpen-for-apple.googlecode.com/svn/wiki/pressureProfiles/hard-20121001.jpg)

![http://hyperpen-for-apple.googlecode.com/svn/wiki/pressureProfiles/soft-20121001.jpg](http://hyperpen-for-apple.googlecode.com/svn/wiki/pressureProfiles/soft-20121001.jpg)

You change the slope of a segment by activating the appropriate slider (checkbox below) and slide it to the desired height. If you just want to interpolate two segments just deactivate the slider in between start and end point.