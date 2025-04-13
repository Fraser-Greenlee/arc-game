# Concepts
symmetry, grid expansion, color filling

# Description
The input defines a small shape with a specific color pattern.
To create the output, expand this shape to cover a larger grid by applying left-right and up-down mirroring, resulting in a pattern with both horizontal and vertical symmetry.
The background color is BLACK, and the shape's colors should remain unchanged.

## Input Representations

### Input 1
```hy
(-> (new-grid (jnp.array [5 5]))
    (draw (jnp.array [0 0]) (apply-texture (jnp.array [[Color.RED Color.GREEN] [Color.BLUE Color.YELLOW]]) (rect-mask (jnp.array [2 2]))))
    (color-background Color.BLACK))
```

### Input 2
```hy
(-> (new-grid (jnp.array [4 4]))
    (draw (jnp.array [0 0]) (apply-texture (jnp.array [[Color.BLUE Color.PINK] [Color.PINK Color.BLUE]]) (rect-mask (jnp.array [2 2]))))
    (color-background Color.BLACK))
```

### Input 3
```hy
(-> (new-grid (jnp.array [3 3]))
    (draw (jnp.array [0 0]) (apply-texture (jnp.array [[Color.ORANGE Color.TEAL] [Color.TEAL Color.ORANGE]]) (rect-mask (jnp.array [2 2]))))
    (color-background Color.BLACK))
```

### Input 4
```hy
(-> (new-grid (jnp.array [6 6]))
    (draw (jnp.array [0 0]) (apply-texture (jnp.array [[Color.YELLOW Color.GREY] [Color.GREY Color.YELLOW]]) (rect-mask (jnp.array [2 2]))))
    (color-background Color.BLACK))
```

## To Output Function
```python
def to_output(expr: hy.models.Expression):
    # Extract grid size and initial texture
    grid_size = expr[1][1]
    texture = expr[2][2][1]
    
    # Return expanded grid with mirrored texture
    return hy_eval("""
      `(-> (new-grid (* 2 ~grid_size))
           (draw (jnp.array [0 0]) (add-quad-mirror (apply-texture ~texture (rect-mask ~grid_size))))
           (color-background Color.BLACK))
    """)
```

This puzzle involves recognizing symmetry and understanding how to expand a pattern through mirroring. The solution requires the student to learn about grid expansion and how to apply left-right and up-down mirroring to achieve a larger symmetric pattern.