CG-flexibleShader
=================

Graphics renderer : supports Flat-shading and Phong-shading (full Phong shading at each pixel with bilinear [screen space] normal interpolation over the triangle.)

* Shader supports Flat-shading

* Phong shading of vertices with linear (screen space) color interpolation over the triangle

* Full Phong shading at each pixel with bilinear (screen space) normal interpolation over the triangle.

* The shading mode is selected by choosing an interpolation mode. 

* The GZ_INTERPOLATE flag selects between 

1. Flat shading
2. Vertex lighting with color interpolation
3. Normal interpolation with each pixel getting a separate lighting computation.

* Supports two light types [ type GzLight (in Gz.h) ]

1. GZ_AMBIENT_LIGHT
2. GZ_DIRECTIONAL_LIGHT

* The direction vector is only valid for directional lights and it is the vector from the scene to the light in image-space.  
  Direction is constant since we're assuming the light is very far away.  Ambient light direction has no meaning and is not used.
  
------------------------------------------------------------------------------------
token						value type	
-----------			     	--------
GZ_RGB_COLOR				GzColor		set default flat-shade color
GZ_INTERPOLATE          	int     	shader interpolation mode 

GZ_DIRECTIONAL_LIGHT        GzLight		add a directional light 
GZ_AMBIENT_LIGHT            GzLight		set ambient light color
GZ_AMBIENT_COEFFICIENT     	GzColor		Ka ambient reflectance coef's
GZ_DIFFUSE_COEFFICIENT      GzColor		Kd diffuse reflectance coef's
GZ_SPECULAR_COEFFICIENT    	GzColor		Ks ambient reflectance coef's
GZ_DISTRIBUTION_COEFFICIENT	float		specular power

Below are flag values used for GZ_INTERPOLATE values

Set GZ_INTERPOLATE as the shader interpolation mode to use
GZ_FLAT			0		// do flat shading with GZ_RBG_COLOR
GZ_COLOR		1       // interpolate vertex color
GZ_NORMALS		2       // interpolate normals
------------------------------------------------------------------------------------
