# Conditional Statements
* Ruby uses standard if, elsif, else conditional statements
* The argument for an if statement must be a boolean (true/false) expression
* Boolean operators are supported in Ruby
  * Logical And: `and`, `&&`
  * Logical Or: `or`, `||`
  * Not: `not`, `!`
* Note: The symbolic forms of and, not actually have a higher precedence than the written forms

## If Statement
* Prototype:
```ruby
if( conditional )
  # Statements/Expressions to do if conditional is true
end
```

## Compound If Statements
* Prototype:
```ruby
if( firstConditional )
  # Statements/Expressions to do if firstConditional is true
elsif( secondConditional )
  # Statements/Expressions to do if secondConditional is true
elsif( thirdConditional )
  # Statements/Expressions to do if thirdConditional is true
else
  # Statements/Expressions to do if none of the conditionals are true
end
```

## If Statement Variations

### Using if as a modifier
* Executes `stuffToDoIfTrue` if `conditional` evaluates to true
* Prototype:
```ruby
stuffToDoIfTrue if( conditional )
```

### Single Line If Statement variant
* Sort of like a single line Bash if statement.
* Note the need for `then` and the semicolon terminating the statements/expressions within the body of the if statement
* Prototype:
```ruby
if( conditional ) then stuffToDoIfTrue; end
```

### Using the unless modifier
* Executes `stuffToDoIfFalse` unless `conditional` evaluates to true
* Prototype:
```ruby
stuffToDoIfFalse unless( conditional )
```

## Case Statement
* Simpler form when you have many if/elsif/else statements to check
* Prototype:
```ruby
case
when( firstConditional )
  # Statements/Expressions to do if firstConditional is true
when( secondConditional )
  # Statements/Expressions to do if secondConditional is true
when( thirdConditional )
  # Statements/Expressions to do if thirdConditional is true
else
  # Statements/Expressions to do if none of the conditionals are true
end
```

## Ternary Operator
* Shorthand for coding if/else statements in Ruby
* Taken from the C Programming Language
* Prototype
```ruby
testConditional ? stuffToDoIfTrue : stuffToDoIfFalse
```
* Example
```ruby
def countArgs( *args )
  numArgs = args.length
  argsPlurality = ( numArgs == 1 ? "argument" : "arguments" )
  printf( "You have provided %d %s.\n", numArgs, argsPlurality )
end

countArgs( "A" )  # => You have provided 1 argument.
countArgs( "A", "B", "C")  # => You have provided 3 arguments
```
