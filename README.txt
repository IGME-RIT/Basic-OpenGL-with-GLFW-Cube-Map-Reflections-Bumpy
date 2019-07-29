Documentation Author: Niko Procopi 2019

This tutorial was designed for Visual Studio 2017 / 2019
If the solution does not compile, retarget the solution
to a different version of the Windows SDK. If you do not
have any version of the Windows SDK, it can be installed
from the Visual Studio Installer Tool

Welcome to the Cubemap Reflection-Bumpy Tutorial!
Prerequesites: Normal Mapping, Reflections-Flat

This tutorial is very simple, but takes quite a bit of 
time to implement. Anyone who has mastered the 
Normal Mapping tutorial and the Reflections-Flat tutorial
will be fully capable of finishing this tutorial without
any explanation at all

In normal mapping, we calculate a normal like this:
	vec3 normal = tbn * normalize(normalFromTexture * 2 - 1);

In Reflections-Flat, we reflect our surface-to-eye 
direction over the vertex normal:
	vec3 reflectedDir = reflect(surfaceToEye, norm);
Then get a color from the skybox like this:
	vec4 skyColor = texture(cubeMap, reflectedDir);
	
All you have to do, is replace the normal in the 
Reflections-Flat tutorial with the normal from the 
normal mapping example, and you're done

How to Improve:
Look at the Reflections-Specular tutorial
It allows some pixels to be more reflective than others
Pixels that aren't reflective will become pixels from the model's texture
Pixels that are reflective will become the skybox pixels
Pixels that are sorta reflective will become a combination of both pixels mentioned above
