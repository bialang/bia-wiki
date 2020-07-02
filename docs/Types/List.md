# List

## builtin `list`

```bia
let empty = list()
let something = list(1, "the second element", 3)
```

## Members

- `push(elements...)` pushes all given elements to the list
- `clear()` empties the list
- `size` the current size of the list
- `capacity` the capacity of the; this value describes after what size a push triggers a resize
- `reserve(capacity)` reserves more space
- `shrink_to_fit()` shrinks the list and releases unused memory
- `empty` if the list is empty
