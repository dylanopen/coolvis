# coolvis: the pattern that's never the same!

> This program uses [my Realms library](https://github.com/dylanopen/realms) for
> lightning-fast 2D graphics at over 500,000 FPS. Check it out!

Coolvis started as a way of teaching my friend some programming. It's now become
a tool for creating mesmerising patterns from nothing but a config file!  
Enjoy the endless entertainment.

## Adding patterns

Found a pattern that looks great? Either open a pull request adding the config
as a toml file to the examples folder, or email your `config.toml` to
[opendylan@proton.me](mailto:opendylan@proton.me).

Good luck pattern scavenging!

## Running coolvis

To install coolvis, either:

- Clone the repository with `git clone` then use `cargo run` to run the program.
- Download the binary executable from the **releases** page.

When running the executable, `coolvis` will autogenerate an example
`config.toml` for you. Simply change the config and reload coolvis: you'll get
a completely new visualisation!

## Parameters & configuration

There are loads of parameters to choose from and it can be hard to know what to
change. Here's what they all do:

`width` and `height`: The width of the window (and canvas). This affects a lot:
a tiny change can completely change the visualisation you see, as it alters
when the square will bounce.

`pixelate`: The number of pixels the square will move each frame. This has the
interesting result of making the image more pixelated as this value increases.  
On very slow computers, increasing this value can improve performance.  

> Note: Currently, the more pixelated an image is, the slower the colors will
> change. This is a known issue but I can't yet see a fix for it! For now, make
> sure you **decrease the color_interval** as you increase the pixelation.

`initial_x` and `initial_y`: The position is the pos of the top-left corner of
the square. While it often doesn't affect the pattern much (often just moving it
or stretching it out) it can have huge effects on how the pattern repeats.

`color_interval`: The number of frames between each change in color. The higher
this value is, the *slower* the color will change.  
Note: for less 'blocky' colors, it is recommended to *decrease* this option
instead of *increasing* the `color_magnitude`. However, this may create some
annoying 'back and forth' gradients. The choice is yours.

`color_magnitude`: The maximum the red, green and blue components (0-255) can
change in each `color_interval`. The higher this value, the *quicker* the color
will change (the opposite of `color_interval`).

`color_red`, `color_green` and `color_blue`: The initial color for the brush
(square). This will affect the starting colors and will ultimately have an
impact on the colors throughout the vis, it is probably the least important
option as it only really affects the start, but it's nice to be able to change.

> All randomness in coolvis (currently just the way the colors develop) is
> entirely based on the 5 color options. This means that, while you can't
> predict or define how the colors develop, you will always get the same
> development of colors when you run the same config. You will also get the
> same color development even if you change other settings. However, if you
> change any of the color values even slightly, the colors will develop
> completely differently.

`speed`: The speed is the number of squares drawn per second. Don't be alarmed
by very high speeds: the speed should generally be between 500 and 10,000,
although I've tested up to 1 million FPS and it manages to maintain it
reasonably well on my computer. Experiment with the speed: it doesn't affect
anything about the patterns created, but it does affect the 'playback' speed of
the vis.

`rect_size`: The width and height of the square (brush). This is quite
self-explanatory: larger brushes will fill the screen quicker. Remember that
because the number of pixels is actually `rect_size` squared, so, for example,
16x16 will look a *lot* smaller than 32x32, despite only being half the width
and height.

Good luck finding patterns, and don't forget to add them to the
[examples folder](examples/) if you find anything cool!

