# Py5Graphics.blue()

Extracts the blue value from a color, scaled to match current [](py5graphics_color_mode).

## Description

Extracts the blue value from a color, scaled to match current [](py5graphics_color_mode).

The `blue()` function is easy to use and understand, but it is slower than a technique called bit masking. When working in `color_mode(RGB, 255)`, you can achieve the same results as `blue()` but with greater speed by using a bit mask to remove the other color components. For example, `blue(c)` and `c & 0xFF` both extract the blue value from a color variable `c` but the later is faster.

This method is the same as [](sketch_blue) but linked to a `Py5Graphics` object. To see example code for how it can be used, see [](sketch_blue).

Underlying Processing method: PGraphics.blue

## Signatures

```python
blue(
    rgb: int,  # any value of the color datatype
    /,
) -> float
```

Updated on March 06, 2023 02:49:26am UTC
