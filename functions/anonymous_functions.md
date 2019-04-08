# Anonymous functions

Define anonymous function with `fn` and `end` keywords.

```elixir
mult = fn a, b -> a * b end

mult.(2, 3) #=> 6

is_function mult #=> true

# check if mult is a function that expects exactly 2 arguments
is_function mult, 2 #=> true
```

Note that a dot `.` between the variable and parentheses is required to invoke an anonymous function. 
The dot ensures there is no ambiguity between calling an anonymous function named mult and a named function.

## They are closures

Anonymous functions are closures and as such they can access variables that are in scope when the function is defined.

```elixir
pow = fn a -> mult.(a, a) end

pow.(3) #=> 9
```
