---
title: 'Starfield face texture research'
draft: false
tags: ['research']
date: 2024-08-08
summary: This file contains information that proves Starfield face diffuse/albedo textures are limited in resolution.
---

### This file contains information that proves Starfield face diffuse/albedo textures are limited in resolution.

When I was trying to retexture Starfield faces, I have noticed that my 4K textures are not as crisp as the texture is. I have checked the textures with a simple 4K UV grid, which confirmed that it was, in fact, blurry, which didn't match the texture resolution.

## Experiment #1
I took this texture, which was generated using Blender. The texture was 4K.

![image](/posts/face-texture-research/image1.png)

But, the texture appeared like this in-game:

![image](/posts/face-texture-research/image2.webp)

![image](/posts/face-texture-research/image3.webp)

For the reference, here is a part of the texture where you can clearly see the pixel scale, which clearly didn't match the in-game appearance:

![image](/posts/face-texture-research/image4.webp)

## Experiment #2

For the next test, it was like this:

| Vanilla | Custom |
| -- | -- |
| ![image](/posts/face-texture-research/image5.png) | ![image](/posts/face-texture-research/image6.webp) |

Was checked using TexDiag.

___

The resulting texture blinked once in CharGenMenu on skin tone change and was pitch black in-game. In those tests, my VRAM usage was like this:

![image](/posts/face-texture-research/vram.webp)

Indicating that vram was not a problem here.

Then, I have resized that texture to 2K, resulting in:

![image](/posts/face-texture-research/image7.png)

That texture loaded correctly, but still appeared downscaled by the game.

![image](/posts/face-texture-research/2k_1.webp)

![image](/posts/face-texture-research/2k_2.webp)

Worth noting, other textures seem alright, like the hair retexture present on the images: it is high resolution, and it doesn't seem to be forcibly downscaled by the game.

___

Let's compare pixel scale:

| | |
| - | - |
| ![image](/posts/face-texture-research/pixelscale_1.png) | ![image](/posts/face-texture-research/pixelscale_2.webp) |

## INI experiments

Changing INI values that vaguely seemed related (bFCTBakeMips=0, bEnableActorUseBakeFCT=0) and then restarting the game, entering chargen, cycling between all the presets and skintones, didn't show any success: it remained the same.

___

Later, I have changed my graphics settings, cycling between all the graphics presets, disabling dynamic resolution, setting the resolution slider to maximum, disabling upscaling, and a lot of other things. Also, I have rebuilt my shader cache by deleting cache files.

# Conclusion

Face diffuse textures seem to get downscaled for some reason, and I know no way of circumventing it in a reasonable way.
