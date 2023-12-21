# GPU Gems Books

[GPU Gems](https://developer.nvidia.com/gpugems/gpugems/contributors)
[GPU Gems 2](https://developer.nvidia.com/gpugems/gpugems2/copyright)
[GPU Gems 3](https://developer.nvidia.com/gpugems/gpugems3/contributors)

# Ray Tracing

[Ray Tracing in One Weekend](https://raytracing.github.io/books/RayTracingInOneWeekend.html)
[Ray Tracing the Next Week](https://raytracing.github.io/books/RayTracingTheNextWeek.html)
[Ray Tracing the Rest of Your Life](https://raytracing.github.io/books/RayTracingTheRestOfYourLife.html)

# DirectX

[3dgep](https://www.3dgep.com/category/graphics-programming/directx/)
[Braynzarsoft](https://www.braynzarsoft.net/viewtutorial/q16390-braynzar-soft-directx-11-tutorials)

## DirectX 12

`ID3D12DescriptorHeap`

A descriptor heap can be considered an array of resource views.  
It can contain Render Target Views (RTV), Shader Resource Views (SRVs), 
Unordered Access Views (UAVs), Constant Buffer Views (CBVs), and Samplers. 
The CBV, SRV, and UAV can be stored in the same heap but RTV and Sampler views 
each require separate descriptor heaps.  

# OpenGL

[Learn OpenGL](https://learnopengl.com/Getting-started/OpenGL)
[Opengl-tutorial](http://www.opengl-tutorial.org/)
[Deferred Shading](https://learnopengl.com/Advanced-Lighting/Deferred-Shading)

## OpenGL Project VS 2017

```
Configuration Properties
  General
    Output Directory: .\
  Debugging
    Working Directory: $(OutDir)
  C/C++
    General/Additional Include Directories: .\common\include
    General/SDL Checks: No
    Precompiled Headers: No
  Linker
    General/Additional Library Directories: .\common\lib
    Input/Additional Dependecies: opengl32.lib;glfw3.lib;glew32s.lib;
```

Using `glew32s.lib` instead of `glew32.lib` requires to add `#define GLEW_STATIC` before the GLEW include:
```
#define GLEW_STATIC
#include "GLEW/glew.h"
```
By doing this I do not need to add the DLL inside the output folder.

