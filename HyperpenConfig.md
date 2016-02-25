# Introduction #

Some of you have wished for a utility to configure the driver. The main feature you needed was a little dialog and circumvent the command line to set the options for your tablet. So I have put together `hyperpenConfig`. You can download the app in the Downloads section.

The following screent shots show you how to use it


# Details #

1. When fired up it shows its main dialog. You see one of the machine's devices that qualifies as a HID device. The configuration is read during application startup. If you connect the tablet after the application is running it won't be recognized.

![http://hyperpen-for-apple.googlecode.com/svn/wiki/hyperpenConfig/hyperpenConfig20120831.jpg](http://hyperpen-for-apple.googlecode.com/svn/wiki/hyperpenConfig/hyperpenConfig20120831.jpg)

2. Select the tablet in the drop down box.

If you only have one tablet connected to your system, it should already be selected. Otherwise you can use the dropdown to select the right one.

3. The tablet's capabilities will be shown.

You can see width and height of the tablet. Next you see that the button (Save Configuration ...) is enabled. By selecting the ratio that matches your screen, you change the logical height of the tablet.

If the aspect ratio of your display and tablet fit, circles you draw on the tablet will apear as such on the screen. Otherwise they will be distorted some way.

4. In the current version (08/31/2012) I have included additional options.

These were available via command line settings but not within the GUI of hyperpenConfig. These are as follows:
  1. Pressure levels allow you to tune the driver to your pen's sensitivity. This is a parameter you have to supply if your stylus supports more than 512 (default) levels. Most current pens support 1024.
  1. Average is an option you can use to reduce the jitter of your tablet. Most tablets report different coordinates when you hold the pen on one position. By averaging the coordinates the jitter is mostly compensated and you can draw smoother lines.
  1. Display ID allows you to restrict the tablet output to just one display in a multimonitor setup. 0 always is the display which owns the menu bar. You can identify the other if you switch to System Preferences -> Displays. If you don't specify a certain display the tablet will be mapped to the whole screen estate available.

5. When you select (Save Configuration ...) a file dialog pops up. Now you navigate to the directory you want to save the driver to. You have the option to create a new directory to host the driver and a command file to start the driver with the right configuration. I have created a directory "test" to store these. Now you select (Save hyperpenDaemon) and the files are saved into this directory.

![http://hyperpen-for-apple.googlecode.com/svn/wiki/hyperpenConfig/4%20save%20config.jpg](http://hyperpen-for-apple.googlecode.com/svn/wiki/hyperpenConfig/4%20save%20config.jpg)

That was the one trick the hyperpenConfig does. You can quit the application and use your tablet with the selected configuration from now on.

6. You find two files in the directory you pointed the application to. One is the driver called "hyperpenDaemon". The other one is the command file "daemonStarter.command". To start the driver with the right configuration you double click on the command file.

![http://hyperpen-for-apple.googlecode.com/svn/wiki/hyperpenConfig/5%20launch%20daemon.jpg](http://hyperpen-for-apple.googlecode.com/svn/wiki/hyperpenConfig/5%20launch%20daemon.jpg)

Happy drawing with your preferred drawing app thereafter.

If you need to reconfigure the tablet later on: Start over at step 1. You can select the same target directory and `hyperpenConfig` will overwrite the command file without further questions.

You can open `daemonStarter.command`with your favorite text editor and change or add parameters manually.