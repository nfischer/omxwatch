omxwatch
========

A script for the raspberry pi to use omxplayer more effectively. If launched in commandline (no gui running), it will clear the screen to create a black background for your movie and then cleanup after viewing.

Purpose
-------
Omxplayer is a great video application for the raspberry pi. It's highly
lightweight and does a decent job at handling various video formats.
But anyone who has ever tried to play a video has noticed one of its main
drawbacks... **It doesn't cover the whole screen!**

The ideal background for omxplayer would be a solid black background that
the video plays on top of, right? So **omxwatch** offers exactly that.

How does it work?
-----------------
Launch omxwatch in the CLI (no gui running) and it will provide you with
a solid black background upon which your video will play. Just type
```
$ omxwatch movieFile.avi
```
and enjoy! Use the same commands as you would use in omxplayer (since this
runs omxplayer internally) such as 'q' to quit the program.

Omxwatch is no secret. It essentially does the following:
- turns off the cursor
- clears the screen
- redirects omxplayer's output to be hidden

And then it plays your movie!

When it exits, all it does is:
- turns the cursor back on
- echoes a nice goodbye message to the terminal

Drawbacks
---------
Because all it does is turn off the cursor and some other things, that means
it needs to be run from the true command line (no gui). Although it works
from a terminal window launched from the gui, it doesn't add any benefit
since you can still see your desktop in the background regardless.

To get to the true command line, you can press ctrl+alt+backspace (if you
had that configured to exit the gui) or you can add that as a feature with:
```
$ raspi-config
```
and then reconfiguring your keyboard (ctrl+alt+backspace comes up as a
special option).

More to Come
------------
What is yet to come? Here are some features I still want to implement for
omxwatch:
- Ability to detect if X is running
- Ability to exit to the commandline for you
- More ability to customize options you want as defaults (i.e. -o hdmi)
- And more...
