# Changelog

## v1.5 (Oct. 11, 2023)
- VR
    - Fixed a bug that caused incorrect rendering when VR HMD roll is not zero (UE5.2 and above).
        - In UE5.1, rendering will not be correct when you tilt head to the left or right. Please use UE5.2 or above.
    - Removed the option for VR ("Advanced > VR" in BP). This setting is no longer required. It just works for both VR and non-VR.
    - Added support for Spherical Harmonics Degrees 1-3 in VR.
    - Improved performance in VR.
- UEFN
    - Fixed a bug that prevented the use in UEFN. Please migrate "NS_3D_Gaussians_sh0_UEFN" to UEFN.

## v1.4 (Oct. 7, 2023)
- Added experimental support for VR.
    - Turn on "Advanced > VR" in details tab of your BP.
    - VR mode supports only Spherical Harmonics Degree 0. We plan to eventually support Degree 1 to 3 as well.
- Added option to tweak sprite size in BP's details tab.
    - Increasing sprite size improves rendering quality, but also increases rendering load.

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