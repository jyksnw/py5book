# select_output()

Opens a file chooser dialog to select a file for output.

## Examples

<div class="example-table">

<div class="example-row"><div class="example-cell-image">

</div><div class="example-cell-code">

```python
def file_selected(selection):
    if selection is None:
        py5.println("Window was closed or the user hit cancel.")
    else:
        py5.println("User selected " + selection)


def setup():
    py5.select_output("Select a file to write to:", file_selected)
```

</div></div>

</div>

## Description

Opens a file chooser dialog to select a file for output. After the selection is made, the selected File will be passed to the `callback` function. If the dialog is closed or canceled, `None` will be sent to the function, so that the program is not waiting for additional input. The callback is necessary because of how threading works.

This method has some platform specific quirks. On OSX, this does not work when the Sketch is run through a Jupyter notebook. On Windows, Sketches using the OpenGL renderers (`P2D` or `P3D`) will be minimized while the select dialog box is open. This method only uses native dialog boxes on OSX.

Underlying Processing method: [selectOutput](https://processing.org/reference/selectOutput_.html)

## Signatures

```python
select_output(
    prompt: str,  # text prompt for select dialog box
    callback: Callable,  # callback function after selection is made
    default_file: str = None,  # default output file
) -> None
```

Updated on March 06, 2023 02:49:26am UTC
