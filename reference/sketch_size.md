# size()

Defines the dimension of the display window width and height in units of pixels.

## Examples

<div class="example-table">

<div class="example-row"><div class="example-cell-image">

</div><div class="example-cell-code">

```python
def setup():
    py5.size(200, 100)
    py5.background(153)
    py5.line(0, 0, py5.width, py5.height)
```

</div></div>

<div class="example-row"><div class="example-cell-image">

</div><div class="example-cell-code">

```python
def setup():
    py5.size(320, 240)


def draw():
    py5.background(153)
    py5.line(0, 0, py5.width, py5.height)
```

</div></div>

<div class="example-row"><div class="example-cell-image">

</div><div class="example-cell-code">

```python
def setup():
    py5.size(150, 200, py5.P3D)  # specify P3D renderer
    py5.background(153)

    # with P3D, we can use z (depth) values...
    py5.line(0, 0, 0, py5.width, py5.height, -100)
    py5.line(py5.width, 0, 0, py5.width, py5.height, -100)
    py5.line(0, py5.height, 0, py5.width, py5.height, -100)

    # ...and 3D-specific functions, like box()
    py5.translate(py5.width//2, py5.height//2)
    py5.rotate_x(py5.PI/6)
    py5.rotate_y(py5.PI/6)
    py5.box(35)
```

</div></div>

<div class="example-row"><div class="example-cell-image">

</div><div class="example-cell-code">

```python
def setup():
    py5.size(200, 400, py5.PDF, 'output.pdf')
    py5.background(153)
    py5.line(0, 0, py5.width, py5.height)
    py5.exit_sketch()  # needed to save and close the output properly
```

</div></div>

</div>

## Description

Defines the dimension of the display window width and height in units of pixels. This is intended to be called from the `settings()` function.

When programming in module mode and imported mode, py5 will allow calls to `size()` from the `setup()` function if it is called at the beginning of `setup()`. This allows the user to omit the `settings()` function, much like what can be done while programming in the Processing IDE. Py5 does this by inspecting the `setup()` function and attempting to split it into synthetic `settings()` and `setup()` functions if both were not created by the user and the real `setup()` function contains a call to `size()`, or calls to [](sketch_full_screen), [](sketch_smooth), [](sketch_no_smooth), or [](sketch_pixel_density). Calls to those functions must be at the very beginning of `setup()`, before any other Python code (but comments are ok). This feature is not available when programming in class mode.

The built-in variables [](sketch_width) and [](sketch_height) are set by the parameters passed to this function. For example, running `size(640, 480)` will assign 640 to the [](sketch_width) variable and 480 to the height `variable`. If `size()` is not used, the window will be given a default size of 100 x 100 pixels.

The `size()` function can only be used once inside a Sketch, and it cannot be used for resizing.

To run a Sketch at the full dimensions of a screen, use the [](sketch_full_screen) function, rather than the older way of using `size(display_width, display_height)`.

The maximum width and height is limited by your operating system, and is usually the width and height of your actual screen. On some machines it may simply be the number of pixels on your current screen, meaning that a screen of 800 x 600 could support `size(1600, 300)`, since that is the same number of pixels. This varies widely, so you'll have to try different rendering modes and sizes until you get what you're looking for. If you need something larger, use `create_graphics` to create a non-visible drawing surface.

The minimum width and height is around 100 pixels in each direction. This is the smallest that is supported across Windows, macOS, and Linux. We enforce the minimum size so that Sketches will run identically on different machines.

The `renderer` parameter selects which rendering engine to use. For example, if you will be drawing 3D shapes, use `P3D`. In addition to the default renderer, other renderers are:

* `P2D` (Processing 2D): 2D graphics renderer that makes use of OpenGL-compatible graphics hardware.
* `P3D` (Processing 3D): 3D graphics renderer that makes use of OpenGL-compatible graphics hardware.
* `FX2D` (JavaFX 2D): A 2D renderer that uses JavaFX, which may be faster for some applications, but has some compatibility quirks.
* `PDF`: The `PDF` renderer draws 2D graphics directly to an Acrobat PDF file. This produces excellent results when you need vector shapes for high-resolution output or printing.
* `SVG`: The `SVG` renderer draws 2D graphics directly to an SVG file. This is great for importing into other vector programs or using for digital fabrication.

When using the `PDF` and `SVG` renderers with the `size()` method, you must use the `path` parameter to specify the file to write the output to. No window will open while the Sketch is running. You must also call [](sketch_exit_sketch) to exit the Sketch and write the completed output to the file. Without this call, the Sketch will not exit and the output file will be empty. If you would like to draw 3D objects to a PDF or SVG file, use the `P3D` renderer and the strategy described in [](sketch_begin_raw).

Underlying Processing method: [size](https://processing.org/reference/size_.html)

## Signatures

```python
size(
    width: int,  # width of the display window in units of pixels
    height: int,  # height of the display window in units of pixels
    /,
) -> None

size(
    width: int,  # width of the display window in units of pixels
    height: int,  # height of the display window in units of pixels
    renderer: str,  # rendering engine to use
    /,
) -> None

size(
    width: int,  # width of the display window in units of pixels
    height: int,  # height of the display window in units of pixels
    renderer: str,  # rendering engine to use
    path: str,  # filename to save rendering engine output to
    /,
) -> None
```

Updated on March 06, 2023 02:49:26am UTC
