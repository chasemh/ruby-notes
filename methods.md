# Ruby Methods

## Basics
* Methods are defined within `def/end`
```ruby
def myMethod( word )
  printf( "Printing the word: %s\n", word )
end

myMethod( "Hello" )  # => Printing the word: Hello
myMethod( "Goodbye" )  # => Printing the word: Goodbye
```
## Default Arguments
* Method arguments can be defined with defaults
```ruby
def myMethod( word = "DEFAULT" )
  printf( "Printing the word: %s\n", word )
end

myMethod( "Hello" )  # => Printing the word: Hello
myMethod()  # => Printing the word: DEFAULT
```

## Variable Arguments
* Methods may also accept a variable amount of arguments
* Variable length arguments are bundled together into an Array
```ruby
def lotsOfWords( *words )
  # words is bundled into an Array
  printf( "Words: " )
  words.each{ |word|
    printf( "%s ", word )
  }
  printf( "\n" )
end

lotsOfWords( "Hello", "Goodbye" )  # => Words: Hello Goodbye
lotsOfWords( "A", "B", "C", "D", "E", "F" ) # => Words: A B C D E F
```

## Aliasing Methods
* Aliasing: Creating a new name for an existing method
* Invocation of an aliased method still points back to the original message
* Provides a means to access methods that have been overwritten
```ruby
def myMethod()
  puts( "You called myMethod!" )
end

alias myNewSweetMethod myMethod
myMethod() # => "You called myMethod!"
myNewSweetMethod() # => "You called myMethod!"
```

* Overwrite Example
```ruby
def myMethod()
  puts( "You called myMethod!" )
end

alias myOriginalMethod myMethod

eval( "def myMethod; puts( 'You called my overwritten method!' ); end" )

myMethod() # => You called my overwritten method!
myOriginalMethod() # => You called myMethod!
```
