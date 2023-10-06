# Changelog

## v1.3 (Oct. 6, 2023)

- Added experimental support for lighting. Lit/Translucent material is now supported, but problems occurs under certain conditions. [See the details](../how-to-import#known-issues).
    - Lumen is not supported.
        - You can receive the light from Global Illumination, but the brightness may be unstable over time. Also, it cannot emit GI light.
    - Shadows are not supported for both receive and cast.
- You can now specify the croppping range by combining multiple volumes.
- Added a fcuntion to hide data in specified ranges. Similar to croppping, it can be specified by combining multiple volumes.
- Fixed a bug that caused the editor would crash during import if the folder structure was under certain conditions.
- Fixed a bug that caused the incorrect sprite size when the FOV is changed from 90 degrees.

## v1.2 (Sep. 24, 2023)
- Added supports for UE 5.1 and 5.2.
- Added options to treat colors as sRGB or linear, which can be set from the Details tab in BP.
- Added [conversion guide](../how-to-unofficial) from the unofficial implementation [taichi_3d_gaussian_splatting](https://github.com/wanmeihuali/taichi_3d_gaussian_splatting)(Apache-2.0)
- Fixed a bug that caused incorrect rendering when the scale of the actor is not 1.
- Fixed a bug that caused actor rotations not to be included in color calculations for Spherical Harmonics Degree 1 and above.

## v1.1 (Sep. 22, 2023)
- Added functions to crop and tweak color, which can be set from the Details tab of the BP.
- Revamped assets for easier [migration to UEFN](../how-to-uefn).  
  Due to this, direct hard references to some assets in "Engine > Plugins > 3D Gaussians Content > Niagara" are no longer be compatible with v1.0.
- Fixed a bug that could cause some gaussians not to be displayed.

## v1.0 (Sep. 19, 2023)
- First release.