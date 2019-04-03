# Elixir guides

Useful information about Elixir Programming language

## Console commands

- `elixir -v` - version of Elixir
- `iex` - run Interactive Elixir mode in terminal
- `elixir hello.exs` - run Elixir script (eg. this script has command: `IO.puts "Hi"`)

## Syntax features

- Elixir allows you to drop the parentheses when invoking named functions:

```
div(10, 3) #=> 3
div 10, 3 #=> 3
```

- Functions in Elixir are identified by both their name and their *arity* (i.e. the number of arguments that the function takes). `div/2` identifies the function which is named `div` and takes 2 arguments.
