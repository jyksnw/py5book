# Py5Graphics.vertices()

Create a collection of vertices.

## Description

Create a collection of vertices. The purpose of this method is to provide an alternative to repeatedly calling [](py5graphics_vertex) in a loop. For a large number of vertices, the performance of `vertices()` will be much faster.

The `coordinates` parameter should be a numpy array with one row for each vertex. There should be two or three columns for 2D or 3D points, respectively.

This method is the same as [](sketch_vertices) but linked to a `Py5Graphics` object. To see example code for how it can be used, see [](sketch_vertices).

Underlying Processing method: PGraphics.vertices

## Signatures

```python
vertices(
    coordinates: npt.NDArray[np.floating],  # 2D array of vertex coordinates with 2 or 3 columns for 2D or 3D points, respectively
    /,
) -> None
```

Updated on March 06, 2023 02:49:26am UTC
