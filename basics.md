# Ruby Basics

## Basic Ideas
* Object oriented language.
* Everything is an object.
* Variables are not declared with types, types are inferred by Ruby at runtime.
  * Called dynamic or duck typing
* Interpreted language. Code is run through the Ruby interpreter.

## Symbols
* Always prefixed by a colon (:)
* A symbol always refers to the same object throughout a Ruby program

## Running System Commands
* Can execute system commands using `system`
* Can also put shell commands in backticks ``
* `exec` is similar to system but it replaces the current process and exits once the command is finished
```ruby
system( "ruby --version" )  # Returns true

puts( "Running " + `ruby --version` )  # Returns nil

exec( "ruby --version" ) # Runs and then exits
```

## String Basics
* Can concatentate strings using `+` and `<<`
```ruby
puts( "Hello " + "World!" ) # => Hello World!

puts( "Hello " << "World!" ) # => Hello World!
```

## Running things multiple times
* Can "multiply" a string in a print command to have it print multiple times
* Can also use the `.times()` method with an integer and pass a block to execute multiple times
```ruby
puts( "Hello! " * 3 ) # => Hello! Hello! Hello!

3.times(){ print( "Hello! " ) } # => Hello! Hello! Hello!
```

## Using eval
* `eval` method accepts a string and evaluates the string as it if were a Ruby expression and then returns the results
* Allows code to be manifested as a primitive data type which Ruby can make sense of.
* Can run any Ruby code in `eval` (Create methods etc.)
* Method of the Kernel module, which is included in the `Object` class, so every object in Ruby can use it
* Can also pass in a binding as the second argument for `eval`
* A binding is an object stores the context or scope of which it lies in
```ruby
result = eval( "10 * 10")
puts( result ) # => 100
```

## Basic User Input
* Use the `gets` method to read user input from the command line
```ruby
input = gets()
printf( "You typed in: %s", input )
```

## Comments
* Line comments begin with `#`
* Block comments inclosed with `=begin ... =end`

## Parallel Assignment
* Can declare and assign multiple variables on a single line in Ruby, similar to Python
```ruby
x, y, z = 10, 20, 30
```

## Statement vs Expression
* Expressions return a value after execution
  * Ex. method call
* Statements do not return a value
  * Ex. if statement

## BEGIN and END blocks
* BEGIN accepts a block that will execute before a program runs
* END accepts a block that will execute after a program exits
* Example
```ruby
BEGIN{ printf( "Date and Time: %s\n", Time.now.to_s() ) }
printf( "In the program!\n")
END{ printf( "End Time: %s\n", Time.now.to_s() ) }
```
