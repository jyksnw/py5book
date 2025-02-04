# Py5Shape.fill()

Sets the color used to fill the `Py5Shape` object.

## Examples

<div class="example-table">

<div class="example-row"><div class="example-cell-image">

![example picture for fill()](/images/reference/Py5Shape_fill_0.png)

</div><div class="example-cell-code">

```python
def setup():
    s = py5.create_shape()
    s.begin_shape()
    s.fill(230, 230, 25)
    s.vertex(20, 80)
    s.vertex(50, 20)
    s.vertex(80, 80)
    s.end_shape(py5.CLOSE)

    py5.shape(s)
```

</div></div>

</div>

## Description

Sets the color used to fill the `Py5Shape` object. For example, if you run `fill(204, 102, 0)`, the shape will be filled with orange. This color is either specified in terms of the `RGB` or `HSB` color depending on the current [](sketch_color_mode). The default color space is `RGB`, with each value in the range from 0 to 255.

This method can only be used within a [](py5shape_begin_shape) and [](py5shape_end_shape) pair.

When using hexadecimal notation to specify a color, use "`0x`" before the values (e.g., `0xFFCCFFAA`). The hexadecimal value must be specified with eight characters; the first two characters define the alpha component, and the remainder define the red, green, and blue components.

When using web color notation to specify a color, create a string beginning with the "`#`" character followed by three, four, six, or eight characters. The example colors `"#D93"` and `"#DD9933"` specify red, green, and blue values (in that order) for the color and assume the color has no transparency. The example colors `"#D93F"` and `"#DD9933FF"` specify red, green, blue, and alpha values (in that order) for the color. Notice that in web color notation the alpha channel is last, which is consistent with CSS colors, and in hexadecimal notation the alpha channel is first, which is consistent with Processing color values.

The value for the "gray" parameter must be less than or equal to the current maximum value as specified by [](sketch_color_mode). The default maximum value is 255.

To change the color of a `Py5Shape` object's image or a texture, use [](py5shape_tint).

Underlying Processing method: PShape.fill

## Signatures

```python
fill(
    gray: float,  # number specifying value between white and black
    /,
) -> None

fill(
    gray: float,  # number specifying value between white and black
    alpha: float,  # opacity of the fill
    /,
) -> None

fill(
    rgb: int,  # color variable or hex value
    /,
) -> None

fill(
    rgb: int,  # color variable or hex value
    alpha: float,  # opacity of the fill
    /,
) -> None

fill(
    x: float,  # red or hue value (depending on current color mode)
    y: float,  # green or saturation value (depending on current color mode)
    z: float,  # blue or brightness value (depending on current color mode)
    /,
) -> None

fill(
    x: float,  # red or hue value (depending on current color mode)
    y: float,  # green or saturation value (depending on current color mode)
    z: float,  # blue or brightness value (depending on current color mode)
    a: float,  # opacity of the fill
    /,
) -> None
```

Updated on March 06, 2023 02:49:26am UTC
