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

* Lights are specified like most everything else, through a call to GzPutAttribute()


