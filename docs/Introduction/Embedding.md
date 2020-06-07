# Embedding

Bia's primary focus is to be easily embeddable into a C++11 application. For this purpose Bia exposes a simple wrapper class `bia::engine` (include `<bia/bia.hpp>`).

## Native Functions

Functions can be added with `function`, like:

```cpp
inline int square(int x)
{
	return x * x;
}

// static function
engine.function("square", &square);
```

## Advanced Functions

```cpp
inline int sum(bia::parameters params)
{
	int s = 0;

	for (auto param : params) {
		if (param) {
			s += bia::cast<int>(*param);
		}
	}

	return s;
}

engine.function("sum", &sum);
```
