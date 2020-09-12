# List

## builtin `list`

```Bia
let empty = list()
let my_list = list(1, "the second element", 3)

for element in my_list {
	io.print(element)
}
```

## Members

- `push(elements...)` pushes all given elements to the list
- `pop(n=1)` removes the last n elements
- `clear()` empties the list
- `size` the current size of the list
- `capacity` the capacity of the; this value describes after what size a push triggers a resize
- `empty` if the list is empty
- `front` the first element of the list
- `back` the last element of the list
- `reserve(capacity)` reserves more space
- `shrink_to_fit()` shrinks the list and releases unused memory
- `insert(index, elements...)` inserts the elements at the given index
- `erase(index, n=1)` erases from index n elements
- `reverse()` reverses the list inplace
