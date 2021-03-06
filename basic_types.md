# Elixir basic types

## Integers

```
10
```
```
is_integer(5) #=> true
```

## Floats

```
5.5
10 / 2 #=> 5.0
10 / 3 #=> 3.3333333333333335
```
```
is_float(3.14) #=> true

is_number 3.14 #=> true
is_number 5 #=> true
```

In Elixir, the operator `/` always returns a `float.

Elixir has a construct called **aliases**. Aliases start in upper case and are also atoms:
```
is_atom Kenny #=> true
```

## Booleans

```
true
false
```
```
is_boolean false #=> true
is_boolean 1 #=> false
```

The booleans `true` and `false` are, in fact, atoms:

```
true == :true #=> true
is_atom false #=> true
```

## Atoms / Symbols

```
:atom
```
```
is_atom :hi #=> true
```

## Strings

Strings in Elixir are delimited by *double quotes*, and they are encoded in UTF-8.

```
"Hello"
```

Single-quoted and double-quoted representations are not equivalent in Elixir 
as they are represented by different types:

```elixir
"hello" == 'hello' #=> false
```

**Interpolation**

```
name = "Kenny"
"Hello #{name}" #=> "Hello Kenny"
```

## Lists

```
length ['hi', true, 123] #=> 3

[1, 2] ++ [true, 4] #=> [1, 2, true, 4]

[1, 2, 4] -- [true, 4] #=> [1, 2]
[4, 1, 2, 4] -- [true, 4] #=> [1, 2, 4]

hd [2, 4, 5] #=> 2
tl [2, 4, 5] #=> [4, 5]
```

Lists are stored in memory as *linked lists*, meaning that each element in a list holds its value and points to the following element until the end of the list is reached. 
This means accessing the length of a list is a linear operation: we need to traverse the whole list in order to figure out its size.

Similarly, the performance of list concatenation depends on the length of the left-hand list.

## Tuples

```
tuple = {:hi, "kenny", 123}

elem tuple, 1 #=> "kenny"

tuple_size tuple #=> 3

put_elem(tuple, 1, "joe") #=> {:hi, "joe", 123}
```

Tuples, on the other hand, are stored contiguously in memory. This means getting the tuple size or accessing an element by index is fast. However, updating or adding elements to tuples is expensive because it requires creating a new tuple in memory.

