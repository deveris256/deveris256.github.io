---
title: '(Experimental) Blender .biom addon'
draft: false
tags: ['projects']
date: 2024-07-23
summary: An addon for editing .biom files, allowing for changing the **resource** and **biome** placements, and swapping biomes.
---

An addon for editing .biom files, allowing for changing the **resource** and **biome** placements, and swapping biomes.

### Download link
https://github.com/deveris256/SF_Planet_Experiments/releases/

___

# Instruction

## Installation
Download from [GitHub releases](https://github.com/deveris256/SF_Planet_Experiments/releases/), don't extract the .zip file. Instead, open Blender, then head to Edit -> Preferences, and enable the addon. If it gives you an error, then open Blender text editor and paste this:

___

```python
import sys, subprocess

subprocess.run([sys.executable, "-m", "pip", "install", "Pillow"])
```
___

Then, run the script.

If it gives another error, replace Pillow text with the module from error, like replacing Pillow with construct, and run the script again.

After that, enable the addon. Addon panel is called **Starfield Planets**, and is located to the right of the viewport (N key).

## How to use

At first, extract the .biom files if you haven't already. You can use [BAE](https://www.nexusmods.com/starfield/mods/165) for extracting game archives. Biome files are located in the **Starfield - PlanetData.ba2** game archive.

Then, load .biom file by pressing the corresponding button in the addon panel.

### Drawing

The addon generates images from the data contained in the .biom file after you load the file. To find and edit these images, you can press the **Open images folder** button at the panel.