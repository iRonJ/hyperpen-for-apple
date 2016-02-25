## Planned features for the coming releases ##

next steps (03/10/2012):
  * commandline option to configure functions keys
  * add action scripts for each function key to override standard actions
  * delegate all tablet events outside the active digitizer area  to a script engine
    * this way the user would be in a position to even override the layout of virtual keys

So now we have left (03/10/2011):
  * gui to query and set tablet status and other parameters (as seen in tablet magic)
    * switch between mouse and tablet mode
  * synthesize tablet status changes via macro keys
    * x,y tilt

following features are already implemented:
  * defining macro keys (done)
  * commandline option to configure pressure threshold (done)
  * easy way to select the usb tablet in question (needed for the naive user) (done)
  * command line arguments (done)
    * vendor and product ids to support other tablet models as well
    * active tablet bounds and extension
  * gui to query and set tablet status and other parameters (as seen in tablet magic)
    * defining macro keys
  * synthesize tablet status changes via macro keys
    * x,y tilt
  * simulate keypresses (done)

following features didn't prove to be needed:
  * switch between mouse and tablet mode