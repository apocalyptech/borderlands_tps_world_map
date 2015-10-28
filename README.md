Borderlands: The Pre-Sequel World Map
=====================================

> **NOTE:** This git repository makes use of github.com's Large File Storage.
> See https://github.com/blog/2069-git-large-file-storage-v1-0 or https://git-lfs.github.com/

This is a world map of all Borderlands: The Pre-Sequel game locations
from the base game, on both Elpis and Helios.  The map does also
include The Abandoned Training Facility.  That area is only available
if the Shock Drop Slaughter Pit DLC is installed, but it's included
because there's a map link to that area regardless of if you have the
DLC.

This map came about because I'd always appreciated having a Borderlands
2 world map, such as the one available here:
http://borderlands.wikia.com/wiki/File:Borderlands_2_Playable_World_Map_made_by_k1ll1ng5pr33.jpg
Such a map didn't seem to exist for Borderlands: TPS, though, so I
took it upon myself to create one.

The individual map images were created (or at least uploaded) by Wikia
user Zuriki, at http://borderlands.wikia.com/wiki/Category:Borderlands:_The_Pre-Sequel_Maps

Feel free to contribute to the map.  I'm sure it could be made prettier,
and it's entirely possible there's some errors in there.  One thing
which struck me while playing around with map placement was that many
of the maps don't really fit well into their in-game Fast Travel map
locations.  The whole line from Outlands Canyon -> Outlands Spur ->
Pity's Fall, in particular, is completely backwards.  I also found
that the layout of the Helios maps looked a lot better reversed.
In the end I was less concerned with fitting the maps into their Fast
Travel map locations than I might have been otherwise.

I'd like to put this under some kind of Creative Commons license, but
the individual map images are probably copyrighted by Gearbox or 2K or
someone.  To paraphrase the licensing information from Wikia on the
map images:

> This map is constructed from screenshots of a non-free copyrighted video game
> or computer game, and the copyright for it is most likely held by the company
> or person that developed the game. It is believed that the use of this
> screenshot by this world map qualifies as fair use under United States
> copyright law, as such display does not significantly impede the right of the
> copyright holder to sell the copyrighted material, is not being used to
> generate profit in this context, and presents ideas that cannot be exhibited
> otherwise. 

Editing Information
===================

The source file is available here as a Gimp XCF file.  Gimp should be available
on Windows, OSX, and Linux, and is available here: http://www.gimp.org/

I'll apologize in advance for any horribly amateurish cruft in that file.  I
do very little graphical work, so I'm sure that there's better ways of doing
just about everything in there.  Nearly every element in there is in its own
layer, which makes shifting individual items around quite easy, though it can
be a pain to relocate a map itself since I don't think Gimp lets you move
multiple layers at the same time like a program like Illustrator or Inkspace.

The official Borderlands font is apparently "Compacta SH Bold."  That font's
only available commercially, for about $26 USD.  The very similar "Compacta BT
Bold" can be very easily found online, though, so that's what I ended up using.
I suspect that Compacta BT Bold is supposed to be a commercial font as well,
so I'll leave acquiring it as an exercise for the reader.

The black border around all the game text was generated with Gimp's "Text to
Path" function, followed by "Stroke Path" using the Paintbrush tool.  If you
want to save yourself a ton of repetetive mindless clicking, I'd recommend
installing a plugin such as https://github.com/apocalyptech/gimp-text-outline
and assign it to a hotkey.

The palette I've used is included in this repository as `TPS-Map.gpl`.  To
install it, just put it in the `palettes` directory in your Gimp configuration
directory.

* On Linux, that'll be `~/.gimp-2.8/palettes/`
* On Windows, it might be something like `C:\Users\[username]\.gimp-2.8\palettes\`

For reference, though, here are the colors that I'd used, in the order they
appear on the palette:

| Color   | Desc             | Uses                                         |
|---------| -----------------|----------------------------------------------|
| #3f4772 | ligher blue      | Individual map highlight background          |
| #000000 | black            | Font outlines                                |
| #16143c | dark blue        | Main map background color                    |
| #e0e0e0 | light gray       | Border around individual map highlights      |
| #ff2d2d | red              | Two-way connections between maps             |
| #fbd13e | dusty yellow     | One-way connections, URLs                    |
| #feed01 | yellow           | Map titles, main title, dividing line border |
| #111027 | really dark blue | Dividing line background                     |
| #ecedfd | more light gray  | All white text                               |

The map highlight outlines, map connections, and dividing lines are all
drawn using Paths, using the "Stroke Path" function and the Paintbrush tool.
For the map highlights, I'd first fill within the path (converting to selection
first), and then stroke along the path.  For the dividing lines, I'd been
doing the opposite: stroking the path first and then filling with the
background color.

I'd used three brushes for the various operations, all of which should be Gimp
default brushes.  In the end it probably doesn't matter which brush is used,
but I figure I should enumerate them here anyway.  All the brushes share the
following attributes:

* Shape: Circular
* Radius: 25.0
* Spikes: 2
* Aspect Ratio: 1.0
* Angle: 0.0
* Spacing: 10.0

The individual brushes are:

* `2. Hardness 050`
  * Hardness: 0.50
* `2. Hardness 075`
  * Hardness: 0.75
* `2. Hardness 100`
  * Hardness: 1.00

All "Stroke Path" operations were done with the Paintbrush tool, with the
following settings (which I believe are the defaults):

* Mode: Normal
* Opacity: 100
* Aspect Ratio: 0
* Angle: 0
* Dynamics: Pressure Opacity
* Checkboxes off for:
  * Apply Jitter
  * Smooth stroke
  * Incremental

The options which would change depending on what I was doing was the brush
setting and the "Size" slider.  These are enumerated here:

* Map highlight outlines
  * Brush: `2. Hardnesss 050`
  * Size: 3
* Connections
  * Brush: `2. Hardness 050`
  * Size: 7
* Map dividing line:
  * Brush: `2. Hardness 075`
  * Size: 2
* Text outlines
  * Main title, "Elpis" and "Helios" labels:
    * Brush: `2. Hardness 100`
    * Size: 30
  * Map names, notes, stuff in the lower-left key/legend
    * Brush: `2. Hardness 100`
    * Size: 10
  * In-level area titles:
    * Brush: `2. Harness 100`
    * Size: 3

Gimp's export to PNG for the map is about 6.3MB or so.  I'll generally
run it through `optipng` after export, which shaves off about 1.1MB.  I
run Linux, where optipng should be freely available.  I'm not sure about
its availability on other platforms, though I assume that if optipng
itself doesn't exist, something else functionally identical must.

```
$ optipng -zc9 -zm9 -zs0 -f0 pre_sequel_world_map.png
```

TODO
====

* It might be nice to indicate vending machines and Moon Zoomy stations
on the map as well.
* It also might be nice to highlight the Fast Travel locations a little
more obviously.
* I'd like to have some better-quality reconstructed icons, rather than
the somewhat-fuzzy versions that I'd taken from screen captures.
* I feel as though the map's "native" size could stand to be smaller.  It's
a bit stupid that the map resolution is bigger than the Borderlands 2 world
map when TPS is about 2/3rds the size.  On the other hand, I always thought
the B2 map was a bit cramped, so clearly I prefer things a little more spread
out.  At any rate, I suspect that shrinking it "properly" at the source level
would take more effort than I'm willing to spend at the moment.
* Now that I'm effectively done with this for the time being, I can't help
but wonder if this should've been implemented in Inkscape instead of Gimp.  I
bet a lot of the shuffling around would have been easier.

Changelog
=========

v1.0 - October 27, 2015 - Initial Release
