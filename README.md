# 4K (HiDPI) rescale Full HD

Using a 4K display and a Full HD display under Linux can cause some problems, often the scaling of the display is done on both or more displays. For example, if you scale a 4K display to 150% or 200%, this scaling is also done on the Full HD display, but this effect is often undesirable. In order to get a uniform scaling and thus a more user-friendly display, you can also have a 4k screen calculated for this display and reduce it to the Full HD display before outputting it.

With this variant, not only the displays of windows and programs remain the same size, but also the mouse pointer, which makes working with multiple displays across screens much easier. 

## The standard tool RandR is needed.

### The old mixed display normally looks like this in the following example (4K & Full HD):
![Preview 1](https://github.com/MTrage/4K-HiDPI-rescale-Full-HD/blob/master/preview/drs1.png)
### The command can be inserted into a SH script, for example, assuming that the 4K display is on the left and the Full HD display is on the right:
    xrandr --output HDMI-0 --scale 2x2 --mode 1920x1080 --fb 7680x2160 --pos 3840x0

![Preview 2](https://github.com/MTrage/4K-HiDPI-rescale-Full-HD/blob/master/preview/drs2.png)
### After a rescale of the 4K resolution for Full HD it looks like this:
![Preview 3](https://github.com/MTrage/4K-HiDPI-rescale-Full-HD/blob/master/preview/drs3.png)

Of course I would be happy if you would integrate this possibility directly on the respective desktop environments to make it a little easier for the user to work. This method works very well but requires a bit more computing power from the graphics card.

## Command and function explanation for the example used
    xrandr --output HDMI-0 --scale 2x2 --mode 1920x1080 --fb 7680x2160 --pos 3840x0

| Options | Stateme | Evaluation function  |
| - | - | -:|
| --output HDMI-0 | Specify the name of the target monitor.<br>A list of all monitor names can be obtained with the following command:  | xrandr --listmonitors |
| --scale 2x2 | Scaling factor for the output. | |
| --mode 1920x1080 | Resolution of the target monitor. | |
| --fb 7680x2160 | Since the displays are on the same 0-line, only the width i.e. 1 times the<br>height and 2 times the 4K-width must be indicated. | |
| --pos 3840x0 | So that the displays lie next to each other<br>(in this case shifted to the right), a 4K width must be added. | |

### If it doesn't work for you or there are other problems with the display mode, please contact me.
