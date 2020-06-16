# Variable assignment

### `var = val` 

Recursively expands variables _at time of use_.

```
var = $(expanded_in_place)
expanded_in_place = these are things

all:
    # Expansion happens here and if $(expanded_in_place) had more variables
    # they would also be expanded.
    echo $(var)
```

### `var := val`

Expand variables once, at the point of assignment.

```
var := things are here

# Expanded at time of assignment
expanded := $(things)
```

