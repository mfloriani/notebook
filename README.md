# GAMEDEV

[C++](Docs/cpp.md)

[Rendering](Docs/rendering.md)

[Math](Docs/math.md)

[Unreal](Docs/unreal.md)

# Misc

- [Networking](https://gafferongames.com/post/fix_your_timestep/)
- [null program - GPU particles](https://nullprogram.com/blog/2014/06/29/)

## 2D Camera

```
// find the world position
world = screen + camera

// find the screen position to an object in the world
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

### Get x/y from tile (cell) id:
```
x = floor( TILE_ID / GRID_WIDTH)
y = TILE_ID mod GRID_WIDTH
```



