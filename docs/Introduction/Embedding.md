# Embedding

Bia's primary focus is to be easily embeddable into a C++11 application. For this purpose Bia exposes a simple wrapper class `bia::engine` (include `<bia/bia.hpp>`).

## Variables

=== "C++"

    ```cpp
    engine.variable("argc", argc);
    engine.variable("pi", 3.141);
    engine.variable("path", std::string{ std::getenv("PATH") });
    ```

## Functions

### Simple Functions

Functions can be added with `function`, like:

=== "C++"
    ```cpp
    inline int square(int x)
    {
        return x * x;
    }

    // static function
    engine.function("square", &square);

    // functor/lambda
    engine.function("special", [](int x) { return x * x; });
    ```

=== "C"
    !!! warning
        This part has not been implemented yet.

    ```c
    static bia_creation_t square(bia_parameters_t params, void* arg)
    {
        bia_parameters_t param = 0;
        bia_creation_t result  = 0;
        double x               = 1.0;

        bia_parameters_at(params, 0, &param);
        bia_member_cast_double(param, &x);
        bia_create_double(x * x, &result);

        return result;
    }

    bia_engine_put_function(engine, "square", &square, 0);
    ```

### Variable Parameters

=== "C++"

    ```cpp
    inline std::ptrdiff_t sum(
        bia::member::function::Varargs<std::ptrdiff_t> params)
    {
        std::ptrdiff_t s = 0;
        for (std::size_t i = 0; i < args.size(); ++i) {
            s += args.at(i);
        }
        return s;
    }

    engine.function("sum", &sum);
    ```

### Type Unions

=== "C++ Static"

    ```cpp
    inline void print(bia::util::Variant<std::ptrdiff_t,
                      std::string> value)
    {
        if (value.is_type<std::ptrdiff_t>()) {
            std::cout << "<int>: " << value.get<std::ptrdiff_t>() << "\n";
        } else {
            std::cout << "<str>: " << value.get<std::string>() << "\n";
        }
    }

    engine.function("print", &print);
    ```

## Objects

Object can be populated like the global namespace with `variable()`, `function()` and `object()`:

=== "C++"

    ```cpp
    auto obj = engine.object("obj");
    args.function("hello", [](std::string s) { std::cout << s << "\n"; });
    args.variable("world", std::string{ "hello world" });
    args.finish();
    ```

## Modules

### Runtime Modules

Runtime modules are just like objects with the only exception that they are not available in the global namespace without any explicit `import` statement. Just like the example in the objects section:

=== "C++"

    ```cpp
    auto obj = engine.module("obj");
    args.function("hello", [](std::string s) { std::cout << s << "\n"; });
    args.variable("world", std::string{ "hello world" });
    args.finish();
    ```

    !!! note
        Note the difference in the first line between `engine.object()` and `engine.module()`.

Usage in Bia:

```bia
import obj
obj.hello(obj.world)
```
