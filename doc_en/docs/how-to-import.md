# Import and place to level

## Import

![](images/how-to-import.png){ loading=lazy }  

1. Select `Window > Import 3D Gaussians` from the menu at the top of the UE editor
2. In the dialog window, select `point_cloud.ply`, the result of 3D Gaussian Splatting training

!!! Failure "The path must contain alphanumeric characters only"
	You cannot import from a path that contains multibyte characters such as Japanese.  
	The path must contain only alphanumeric characters.

!!! Failure "Folder structure restrictions"
	Folder structure must be "*ModelName* > point_cloud > iteration_n"

## Place to level

![](images/how-to-place.png){ loading=lazy }  

1. Drag and drop "BP_3D_Gaussians_*ModelName*" onto the level in the content browser under "Content > ThreeDGaussians > *ModelName*".

Also, if necessary, set the following items under "Default" in the Details tab.

2. Specify the culling range with "Bound Min" and "Bound Max".
3. Turn off "SRGB" if the original data is in linear color. If "SRGB" is turned on, the data is treated as sRGB.
4. Tunr on "Mesh" to draw ellipsoids of the size of the Gaussians. This is mainly used for debugging.