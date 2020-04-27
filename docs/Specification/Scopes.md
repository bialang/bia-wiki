# Scopes

## Global Scope

In the global scope all variables are stored with their names in a dictionary. This dictionary is accessible from everywhere in the code.

## Local Scope

Local scopes are defined at function level and opened/closed with `{` and `}` respectively.

```bia
let x = 0 # global

if true { # not a scope
	let y = 0 # still global
}

func foo() { # local scope at function level
	let l = 0

	return func() { # another local scope, can see all scope above but not the other way around
		return l
	}
}
```

## Variable Capturring

## Chained Scopes