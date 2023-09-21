# Import and place to level

## Import

![](images/how-to-import.png){ loading=lazy }  

1. Select `Window > Import 3D Gaussians` from the menu at the top of the UE editor
2. In the dialog window, select `point_cloud.ply`, the result of 3D Gaussian Splatting training

!!! Failure "The path must contain alphanumeric characters only"
	You cannot import from a path that contains multibyte characters such as Japanese.  
	The path must contain only alphanumeric characters.

!!! Failure "Folder structure rule"
	Folder structure must be "*ModelName* > point_cloud > iteration_*nnnnn*"

## Place to level

![](images/how-to-place.png){ loading=lazy }  

1. Drag and drop "Content > ThreeDGaussians > *ModelName* > BP_3D_Gaussians_*ModelName*" onto the level in the content browser.

Also, if necessary, set the following items under "Default" in the Details tab.

- **Enabled Blocks**: Select which blocks of imported data will be displayed.
- **Spherical Harmonics Degree**: Select the color rendering method.  
	"Degree 0" disables the color change depending on the angle of view (no reflections, etc.).  
	"Degrees 1-3" enable the color change with viewing angle. A higher Degree makes the rendering more accurate, but increases the rendering load.  
- **Albedo Tint**: Correct color. The color specified here will be multiplied by the original color.
- **Crop** and **Crop Volume**: Enable the check box and specify the range to crop.
- **Min translucent sort priority**: Sets the priority for rendering 3D Gaussian Splatting data.  
	In this plug-in, 3D Gaussian Splatting data is drawn as a translucent mesh.  
	This value is applied to the `Translucency Sort Priority` of the furthest block, and a value of (this value + number of valid blocks - 1) is applied to the nearest block.
	