# reset_py5()

Reset the py5 module's current `Sketch` instance.

## Examples

<div class="example-table">

<div class="example-row"><div class="example-cell-image">

</div><div class="example-cell-code">

```python
import py5

assert py5.is_ready
first_sketch = py5.get_current_sketch()
py5.run_sketch(block=False)
py5.exit_sketch()
assert py5.is_dead
py5.reset_py5()
assert py5.is_ready
second_sketch = py5.get_current_sketch()
assert first_sketch is not second_sketch
```

</div></div>

</div>

## Description

Reset the py5 module's current `Sketch` instance.

When coding py5 in module mode, a Sketch instance is created on your behalf that is referenced within the py5 module itself. That Sketch is called the "Current Sketch." If the current Sketch exits, it will be in a dead state and cannot be re-run. `reset_py5()` will discard that exited Sketch instance and replace it with a new one in the ready state.

If `reset_py5()` is called when the current Sketch is in the ready or running states, it will do nothing and return `False`. If `reset_py5()` is called when the current Sketch is in the dead state, `reset_py5()` will replace it and return `True`.

## Signatures

```python
reset_py5() -> bool
```

Updated on March 06, 2023 02:49:26am UTC
