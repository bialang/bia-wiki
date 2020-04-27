# Embedding

Bia's primary focus is to be easily embeddable into a C++11 application.

## Adding functions

Functions can be added with `add_func`, like:

```cpp
// static function
engine.fun("some_function", &some_function);

// lambda function
engine.fun("special_function", [&] (int x) {/* cool stuff */});

// member function
engine.add_class<some_class>("some_class")
	.fun("some_function", &some_class::some_function);
```

## Functions with default parameters

Functions can have default parameters which are default constructed if not provided in the Bia script. The amount of optional parameters is given as template values:

```cpp
void add(int x0, int x1, int x2, int x3)
{
	std::cout << "result: " << x0 + x1 + x2 + x3 << "\n";
}

engine.add_func<2>("weird_add", &add);
```

With this the following Bia script is valid:

```
// these all work because the int parameters are default constructed and get a value of 0
weird_add(1, 2)
weird_add(1, 3, 4)
weird_add(4, 2, 1, 4)

// doesn't work because at least on parameter is missing
weird_add(1)
```

## Adding classes

Classes can be added with `add_class`. The returned object represents the class view.