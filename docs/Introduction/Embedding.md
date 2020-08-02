# Embedding

Bia's primary focus is to be easily embeddable into a C++11 application. For this purpose Bia exposes a simple wrapper class `bia::engine` (include `<bia/bia.hpp>`).

## Native Functions

Functions can be added with `function`, like:

```C++ tab=
inline int square(int x)
{
	return x * x;
}

// static function
engine.function("square", &square);

// functor/lambda
engine.function("special", [](int x) { return x * x; });
```

```C tab=
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

## Advanced Functions

### Variable Parameters

```C++ tab=
inline int sum(bia::connector::parameters_type params)
{
	int s = 0;

	// all parameters
	for (auto param : params) {
		if (param) {
			s += bia::cast<int>(*param);
		}
	}

	return s;
}

engine.function("sum", &sum);
```

### Generators

```C++ tab=
#include <bia/member/function/generator.hpp>

inline bia::gc::gcable<bia::member::member> read_lines(const char* filename)
{
	const auto file = std::make_shared<std::fstream>(filename);

	if (!file->is_open()) {
		return {};
	}

	auto generator = [file]() -> bia::gc::gcable<bia::member::member> {
		std::string line;

		if (std::getline(*file, line)) {
			return bia::creator::create(line);
		}

		return bia::member::function::stop_iteration;
	};

	return bia::gc::gc::active_gc()
	    ->construct<bia::member::function::generator<
	        bia::member::function::method<false, decltype(&decltype(generator)::operator())>>>(
	        generator, &decltype(generator)::operator());
}
```
