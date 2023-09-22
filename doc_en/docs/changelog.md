# Changelog

<!-- ## v1.2 (Sep. ??, 2023)
- Added options to treat colors as sRGB or linear, which can be set from the Details tab in BP.
- Added [conversion guide](../how-to-unofficial) from the unofficial implementation [taichi_3d_gaussian_splatting](https://github.com/wanmeihuali/taichi_3d_gaussian_splatting) (Apache-2.0)
- Fixed a bug that caused incorrect rendering when the scale of the actor is not 1.
- Fixed a bug that caused actor rotations not to be included in color calculations for Spherical Harmonics Degree 1 and above. -->

## v1.1 (Sep. 22, 2023)
- Added functions to crop and tweak color, which can be set from the Details tab of the BP.
- Revamped assets for easier [migration to UEFN](../how-to-uefn).  
  Due to this, direct hard references to some assets in "Engine > Plugins > 3D Gaussians Content > Niagara" are no longer be compatible with v1.0.
- Fixed a bug that could cause some gaussians not to be displayed.

## v1.0 (Sep. 19, 2023)
- First release.