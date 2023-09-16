# FAQ

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

## Is 3D Gaussian Splatting a family of photogrammetry?

No, the underlying mechanisms are very different.

## Is 3D Gaussian Splatting a family of NeRF?

No, the underlying mechanisms are very different.

## Is 3D Gaussian Splatting a family of Differentiable Rendering?

Yes.