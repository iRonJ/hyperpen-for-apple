This page summarizes some things related to tablets and drivers.

# Introduction #

While working on the driver I stumbled over several issues I would like to share.

## Macro Keys ##

Some tablets have built-in keys you can really press or softkeys you can choose with the stylus. Based on the 12000U I have designed the driver to handle 24 softkeys. These softkeys are arranged on top of the drawing area.

I used the imprinted labels (as seen on Windows) to guide the actions I've implemented. Some of these actions consist of a keypress (e.g. cmd-c for copy) others invoke an Apple Script script to activate chosen applications (e.g. Microsoft Word or Safari).

Several users have asked for a way to customize the actions and override the built-in actions. I've come up with a solution that relies on command scripts. Every key now has a corresponding command file named **`##.command`**. These files reside in the **`common/`** directory below the driver. ## stands for the number of the key (1-9 preceded by a 0). So **`common/12.command`** is the command invoked when the user picks no 12 with the stylus. You can carry out anything in the script based on your scripting experience (csh, sh, osascript) - whatever comes to your mind.

Here is an example to start Microsoft Word from Apple Script:
```
#!/usr/bin/osascript
tell application "Microsoft Word" to activate
```

The command file needs to be executable by the system. So you need to either **`chmod 755 12.command`** in the shell or use **`06.command`** as a boiler plate.

## Tablet Keys ##
For those of you who don't even have softkeys on their tablets I've added virtual tablet keys as an experimental feature to the current driver.

These virtual tablet keys are available if you use your 4:3 tablet in 16:9 or 16:10 mode.

**Original Tablet**

![http://hyperpen-for-apple.googlecode.com/svn/wiki/tabletKeys/originalTablet.jpg](http://hyperpen-for-apple.googlecode.com/svn/wiki/tabletKeys/originalTablet.jpg)

**Rescaled Tablet**

![http://hyperpen-for-apple.googlecode.com/svn/wiki/tabletKeys/rescaledTablet.jpg](http://hyperpen-for-apple.googlecode.com/svn/wiki/tabletKeys/rescaledTablet.jpg)

**Tablet Keys**

![http://hyperpen-for-apple.googlecode.com/svn/wiki/tabletKeys/Untitled.jpg](http://hyperpen-for-apple.googlecode.com/svn/wiki/tabletKeys/Untitled.jpg)

Using **`-t`** you activate the feature tablet keys. This way you gain an otherwise wasted tablet estate below the active area. I've divided this strip into 8 sections which behave like the softkeys described above. They use the same command files for the time being. In a further step I will use another naming convention for these keys. This way even on 12000U you will benefit from 8 additional keys (=32 if you count the 24 softkeys).


## Aspect Ratio ##

Most tablets still arrive in the width:height ratio 4:3. Modern MacBooks come with a 16:9 or even 16:10 ratio. If not addressed properly this will disort your images somehow. You have a longer way to travel the height of the tablet than there is screen space.

Let's do a little calculation:
  * my 12000U has a resolution of 6000x4500 which gives it a perfect 4:3 ratio
  * the screen of my MacBook shows as 1280x800 which reads as 16:10 (changing screen size isn't an opportunity)
  * using 16:10 ratio the active height of the tablet should be restricted to 3750
  * this leads to a modified resolution of 6000x3750 needed for the tablet

  * using 16:9 ratio the active height of the tablet should be restricted to 3375
  * this leads to a modified resolution of 6000x3375 needed for the tablet

Changing the effective resolution is done with options -w and -h respectively. The resulting command for 16:10 ratio:
```
./hyperpen -w 6000 -h 3750
```

Going for Hypern Pen Mini which has a width of 12288 leads to a height of 7680:
```
./hyperpen -w 12288 -h 7680 -v 0x172f -p 0x37
```

## User Response ##

Somehow it's interesting to see how many people actually download the driver. There seems to be a real need for it. To date two users have responded to my wish to get some feedback. Both of them seemed quite happy with the driver.

I would like others to respond as well. So I can learn which tablets the driver works with. Others would profit as well - cause the setting for their specific tablet would be known/documented.

## Launching Daemon at System Startup ##

It would be convenient for the average user to launch the driver during system startup. At the moment I am still developing the driver, so it wouldn't be helpful in my setting. Although I describe how you could achieve it.

You need to add information to two directories:
  * `/Library/Application Support/`
  * `/Library/LaunchAgents/`

... to be continued soon