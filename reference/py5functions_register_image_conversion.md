# register_image_conversion()

Register new image conversion functionality to be used by [](sketch_convert_image).

## Examples

<div class="example-table">

<div class="example-row"><div class="example-cell-image">

</div><div class="example-cell-code">

```python
import numpy as np

# toy example that converts tuples to grayscale images
def precondition(obj):
    if not isinstance(obj, tuple) or len(obj) != 3:
        return False
    return all(isinstance(x, int) for x in obj)


def convert_function(obj):
    array = np.full((obj[1], obj[2]), obj[0], dtype=np.uint8)
    return py5.NumpyImageArray(array, 'L')


py5.register_image_conversion(precondition, convert_function)


def setup():
    img1 = py5.convert_image((20, 30, 40))
    img2 = py5.convert_image((100, 20, 80))
    py5.println(type(img1))
    py5.println(type(img2))
    py5.image(img1, 30, 50)
    py5.image(img2, 10, 20)
```

</div></div>

</div>

## Description

Register new image conversion functionality to be used by [](sketch_convert_image).  This will allow users to extend py5's capabilities and compatability within the Python ecosystem.

The `precondition` parameter must be function that accepts an object as a parameter and returns `True` if and only if the `convert_function` can successfully convert the object.

The `convert_function` parameter must be a function that accepts an object as a parameter and returns either a filename that can be read by [](sketch_load_image), a `py5.NumpyImageArray` object, or a [](py5image) object. View py5's source code for detailed information about `py5.NumpyImageArray` objects.

## Signatures

```python
register_image_conversion(
    precondition: Callable,  # predicate determining if an object can be converted
    convert_function: Callable,  # function to convert object to relevant image data
) -> None
```

Updated on March 06, 2023 02:49:26am UTC
