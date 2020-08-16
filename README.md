# nvoc
Nvidia overclocking script for Linux (useful for autostarting!)

Because I didn't want tools like GWE to launch on autostart and be on the background just to apply my overclock.  
This just applies the clocks and exits. It's useful in that there is no way to save overclocks on Linux/Nvidia and they are
lost on every reboot, so nvoc fills in that gap.

Needs the proprietary Nvidia drivers to work.
Doesn't use root (so don't expect nvidia-smi functionality such as watt power limits on the future)

Grab the zip, unzip it and have a look at the script file.  
Edit the file and set your preferred clocks in the Options section. 
Make the script executable. Run `chmod +x nvoc`
Then place the script in `/usr/bin`. Then, run `nvoc` to have it apply your settings.

If you have more than one Nvidia GPU installed you'll need to have multiple copies of the script for each GPU, you'll just need to put gpu=1 in the second copy, for example, and so on. You could name them nvoc-0, nvoc-1,... as long as you put them in `/usr/bin` or somewhere else in the PATH.

The whole point of nvoc is to have it autostart with the desktop session.
To have it autostart with the desktop, open a terminal and run:  
`nano ~/.config/autostart/nvoc.desktop`

Then, paste in the following and save (Ctrl+X)
```
Exec=nvoc
Icon=system-run
Name=nvoc
OnlyShowIn=
Path=
Terminal=False
Type=Application
```
All done. Overclocks will now be applied as soon as you log into your desktop.  
If you don't use a desktop (say, on a coin mining headless box) you could have the script run on boot via cron.
