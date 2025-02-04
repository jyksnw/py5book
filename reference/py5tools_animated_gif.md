# py5_tools.animated_gif()

Create an animated GIF using a running Sketch.

## Examples

<div class="example-table">

<div class="example-row"><div class="example-cell-image">

</div><div class="example-cell-code">

```python
import py5_tools

py5.run_sketch()
# create a 10 frame animated GIF saved to '/tmp/animated.gif'
py5_tools.animated_gif('/tmp/animated.gif', 10, 1, 0.5)
```

</div></div>

</div>

## Description

Create an animated GIF using a running Sketch.

By default the Sketch will be the currently running Sketch, as returned by [](py5functions_get_current_sketch). Use the `sketch` parameter to specify a different running Sketch, such as a Sketch created using Class mode.

By default this function will return right away and construct the animated gif in the background while the Sketch is running. The completed gif will be saved to the location specified by the `filename` parameter when it is ready. Set the `block` parameter to `True` to instruct the method to not return until the gif construction is complete. This blocking feature is not available on OSX when the Sketch is executed through an IPython kernel. If the Sketch terminates prematurely, no gif will be created.

If your Sketch has a `post_draw()` method, use the `hook_post_draw` parameter to make this function run after `post_draw()` instead of `draw()`. This is important when using Processing libraries that support `post_draw()` such as Camera3D or ColorBlindness.

## Signatures

```python
animated_gif(
    filename: str,  # filename of GIF to create
    count: int,  # number of Sketch snapshots to create
    period: float,  # time in seconds between Sketch snapshots
    duration: float,  # time in seconds between frames in the GIF
    *,
    loop: int = 0,  # number of times for the GIF to loop (default of 0 loops indefinitely)
    optimize: bool = True,  # optimize GIF palette
    sketch: Sketch = None,  # running Sketch
    hook_post_draw: bool = False,  # attach hook to Sketch's post_draw method instead of draw
    block: bool = False  # method returns immediately (False) or blocks until function returns (True)
) -> None
```

Updated on March 06, 2023 02:49:26am UTC
