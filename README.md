# GAMEDEV

## 2D Camera

```
//find the world position
world = screen + camera

//find the screen position to an object in the world
screen = world - camera
```

## Tiling

### Get x/y index inside grid based on mouse position
```
// 1 - convert mouse coord to world coord
mouse_x = get_mouse_x() + camera_offset_x
mouse_y = get_mouse_y() + camera_offset_y

// 2 - get tile indexes in the grid
tile_x = floor(mouse_x / TILE_WIDTH)
tile_y = floor(mouse_y / TILE_HEIGHT)
```

### Get tile (cell) id in the grid from x/y index (see above)
```
id = tile_y * GRID_WIDTH + tile_x
```

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
