# print_line_profiler_stats()

Print the line profiler stats initiated with [](sketch_profile_draw) or [](sketch_profile_functions).

## Examples

<div class="example-table">

<div class="example-row"><div class="example-cell-image">

</div><div class="example-cell-code">

```python
import time


def draw():
    py5.stroke(py5.random_int(255), py5.random_int(255), py5.random_int(255))
    # this should use `points` instead
    for _ in range(100):
        py5.point(py5.random_int(py5.width), py5.random_int(py5.height))


py5.profile_draw()
py5.run_sketch()


# let the sketch run for a bit to accumulate data
time.sleep(10)

py5.print_line_profiler_stats()
```

</div></div>

</div>

## Description

Print the line profiler stats initiated with [](sketch_profile_draw) or [](sketch_profile_functions). The collected stats will include the number of times each line of code was executed (Hits) and the total amount of time spent on each line (Time). This information can be used to target the performance tuning efforts for a slow Sketch.

This method can be called multiple times on a running Sketch.

## Signatures

```python
print_line_profiler_stats() -> None
```

Updated on March 06, 2023 02:49:26am UTC
