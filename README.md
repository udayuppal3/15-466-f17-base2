NOTE: please fill in the first section with information about your game.

# *Tree Pop*

*Tree Pop* is *Uday Uppal*'s implementation of [*Spider Pop*](http://graphics.cs.cmu.edu/courses/15-466-f17/game2-designs/bebert/) for game2 in 15-466-f17.

![Image](screenshots/screenshot.png?raw=true "Image")

## Asset Pipeline

The asset pipeline consists of a blender file called spiders.blend and an export-meshes.py script used to export information from the blender file into usable scene objects. These objects can then be created and controlled through their transformations in game.

## Architecture

The architecture follows largely the original base2 implementation. Instead of spawing in objects from the blender hierarchy directly, I create object types based on their meshes and save references to them. Then I can easily manipulate them through their transformations from within the game loop. 

## Reflection

I had never before worked with blender, and learning how to work and script with it was difficult. Since the project was very short, I did not have enough time to learn how to use blender properly, and needed to base my work largely on the functionality offered by the base code. I used the tree and rock models since it was difficult to create spiders as I needed to as per the game design. If I were doing the project again, I would have tried to plan more time for it since this week was too busy and I could devote as much time to learning how to use blender as I would have liked in order to use it as effectively as possible.

The design document was very open-ended and left a lot up for interpretation. It made it clear what the objective of the game was, but did not clarify how lives were counted and what it meant to "miss" the food. I resolved this by deciding that food would show up at random, and if the player clicks the wrong key then it would count as a miss. The game would end once the player has tried to jump the wrong tree 3 times.

# About Base2

This game is based on Base2, starter code for game2 in the 15-466-f17 course. It was developed by Jim McCann, and is released into the public domain.

## Requirements

 - modern C++ compiler
 - glm
 - libSDL2
 - libpng
 - blender (for mesh export script)

On Linux or OSX these requirements should be available from your package manager without too much hassle.

## Building

This code has been set up to be built with [FT jam](https://www.freetype.org/jam/).

### Getting Jam

For more information on Jam, see the [Jam Documentation](https://www.perforce.com/documentation/jam-documentation) page at Perforce, which includes both reference documentation and a getting started guide.

On unixish OSs, Jam is available from your package manager:
```
	brew install ftjam #on OSX
	apt get ftjam #on Debian-ish Linux
```

On Windows, you can get a binary [from sourceforge](https://sourceforge.net/projects/freetype/files/ftjam/2.5.2/ftjam-2.5.2-win32.zip/download),
and put it somewhere in your `%PATH%`.
(Possibly: also set the `JAM_TOOLSET` variable to `VISUALC`.)

### Bulding
Open a terminal (on windows, a Visual Studio Command Prompt), change to this directory, and type:
```
	jam
```

### Building (local libs)

Depending on your OSX, clone 
[kit-libs-linux](https://github.com/ixchow/kit-libs-linux),
[kit-libs-osx](https://github.com/ixchow/kit-libs-osx),
or [kit-libs-win](https://github.com/ixchow/kit-libs-win)
as a subdirectory of the current directory.

The Jamfile sets up library and header search paths such that local libraries will be preferred over system libraries.
