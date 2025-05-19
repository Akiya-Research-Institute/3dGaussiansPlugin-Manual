# Changelog

## v1.14 (May. 16, 2025)
- Only UE5.3 and above have been updated.
- Fixed a problem that prevented importing data from Postshot.

## v1.13 (Jan. 26, 2025)
- Only UE5.3 and above have been updated.
- Fixed a problem that prevented importing data on Windows11

## v1.12 (Nov. 24, 2024)
- Only UE5.3 and above have been updated.
- Added runtime load function. [See details](../how-to-runtimeload).

## v1.11 (Sep. 1, 2024)
- Only UE5.2 and above have been updated.
- Fixed flickering problem on data with a large drawing area.
    - If the above problem occurs, set "Project Settings > Plugins > Niagara > Renderer > Default Sort Precision" to "High".
- Fixed rendering problem when screen aspect ratio is portrait.

## v1.10 (Apr. 3, 2024)
- Fixed a problem that prevented importing data exported from Polycam.

## v1.9 (Nov. 28, 2023)
- Added a new rendering method compatible with SceneCapture2D and others.  
	The result is not strictly accurate, but it is more compatible with the engine's rendering pipeline and works in many cases, including SceneCapture2D.

## v1.8 (Nov. 16, 2023)
- Added an option to control the size of the gaussians in the Niagara System. [See details](../how-to-niagara/#use-your-own-niagara).
- .ply files output by Super Splat v0.10.3 are now supported.

## v1.7 (Oct. 26, 2023)
- Added a function to merge multiple models and export them to a single .ply file, with cropping etc. applied. [See details](../how-to-export).

## v1.6 (Oct. 21, 2023)
- Platforms
    - Added experimental support for Ubuntu 22.04 Desktop x64 as a development platform
    - Added experimental support for Linux x64 and Android as target build platforms
- Niagara Emitter now functions correctly when "Local Space" is turned on.
    - If you want to move 3D Gaussians Splatting actors at runtime using Sequencer etc., please turn on "Local Space". [See details](../how-to-niagara).
- Now you can specify the Niagara System to be used. In the details tab of the BP, specify "Advanced > Niagara Override".
    - Added examples using Wind Force and Curl Noise. [See details](../how-to-niagara/#use-your-own-niagara)。

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