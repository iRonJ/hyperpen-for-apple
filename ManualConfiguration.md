## Options ##

If you start the driver from the command line with option _-?_ it will show you the available options:
```
hyperpenDaemon [-v ID] [-p ID] [-w WIDTH] [-h HEIGHT] [-x X-OFFSET] [-y Y-OFFSET] [-c COMPENSATION] [-a {1|2|3|4}]

  -v ID				set vendor  (e.g. 0x08ca)
  -p ID				set product (e.g. 0x0010)
  -w WIDTH			set tablet width  (e.g. 6000)
  -h HEIGHT			set tablet height (e.g. 4500)
  -l LEVEL			set pressure level (0=512, 1=1024, 2=2048, 4=4096)  
  -x X-OFFSET		set tablet x offset (e.g. 0)
  -y Y-OFFSET		set tablet y offset (e.g. 0)
  -c COMPENSATION	compensate mechanical restriction (0-256)
  -a {1|2|3|4}		averages multiple samples to reduce jitter (1=2 samples, 4=16 samples)
  -W WIDTH			set screen width  (e.g. 1920)
  -H HEIGHT			set screen height (e.g. 108)
  -X X-OFFSET		set screen x offset (e.g. 0)
  -Y Y-OFFSET		set screen y offset (e.g. 0)
  -d  displayID		restrict tablet to displayID only
```

The options shown in the first line are only a subset of the available options. The full set of official options are shown above.

## Examples ##

If you use the Terminal application you can supply additional options to the daemon when it starts up. On the one hand you can try to use the driver for other tablets if you have Vendor id and Product id at hand. On the other hand you can restrict the active drawing area of your tablet if you don't want to move the pen around the 12 inches you purchased with the 12000U.

To restrict the active area to a quarter of the tablet, you can use:
```
./hyperpenDaemon -w 3000 -h 2250
```

To change the vendor and product you can use:
```
./hyperpenDaemon -v 0x47 -p 0x20
```
Please note that you use hexadecimal notation to change the personality of the tablet. Have a look at WhichProduct how to find the correct values for these keys.

If you need to compensate a mechanical weakness of the pen, you can use:

```
./hyperpenDaemon -c 128
```

Normally the pen measures pressure levels between 0 and 1023. Some pens don't reset to 0 but stay with a larger value instead. The example shows a way to compensate for a pen not going to a pressure smaller than 127.