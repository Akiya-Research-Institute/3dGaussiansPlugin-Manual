# FAQ

## How can I make packages for platforms other than Windows?

The development team has only tested on Windows, so we cannot guarantee that it will work, but the rendering process is implemented in the standard Niagara and Material nodes, so there is a good chance that it will work on non-Windows platforms.  

To create the package for non-Windows platforms, you need to add the platforms to line 22 of "C:\Program Files\Epic Games\UE_5.3\Engine\Plugins\Marketplace\ThreeDGaussians\ThreeDGaussians.uplugin".

## How do I reduce the package size?

- Set the Spherical Harmonics Degree to "Degree 0".
- Delete "sh1" to "sh11" texture assets in the content browser.
  You will get a reference relationship warning when deleting, but force the deletion.

## How do I get it to work with UEFN?

Documentation is under construction. Please wait a while.

## I placed the imported BP to a level, but nothing hoppens

- Make sure one or more of the EnbaledBlocks are set to True.
- Make sure that the real-time rendering of viewport is turned on. (Ctrl+R)

## Editor crashes when I placed the imported BP to a level

Most likely there is not enough memory on the GPU. Please try the following

- Enable only one or a few of EnbaledBlocks
- Place BP on an empty level

## Rendering result is incorrect

- When [Split by Morton Order](../how-to-split/#split-by-morton-order), check while Play In Editor. The rendering order is sorted only during Play.
- When [Split by the distance](../how-to-split/#split-by-the-distance), the blocks are correctly rendered only when camera is placed in the block nearest to the origin.

## [Official Implementation of 3D Gaussian Splatting](https://repo-sam.inria.fr/fungraph/3d-gaussian-splatting/) is not available for commercial use, how about this plugin?

- This plugin is implemented from scratch using Niagara and Material's node-based programming without any source code from the official implementation. (It does not even contain CUDA or HLSL source code).
  Therefore, this plugin itself is available for commercial use just like any other product in the Unreal Engine Marketplace.
- However, the user is responsible for the origin of the data created by the user. Data created in a manner forbidden for commercial use cannot be used for commercial purposes.
- Note that in addition to the official implementation, there is an MIT-licensed [unofficial implementation](https://github.com/WangFeng18/3d-gaussian-splatting) but it is not directly supported by this plugin.

## Is 3D Gaussian Splatting a family of photogrammetry?

No, the underlying mechanisms are very different.

## Is 3D Gaussian Splatting a family of NeRF?

No, the underlying mechanisms are very different.

## Is 3D Gaussian Splatting a family of Differentiable Rendering?

Yes.