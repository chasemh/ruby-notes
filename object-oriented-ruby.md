# Object Oriented Ruby
* Everything in Ruby is an object
* `Object` class is the parent class for all other classes in Ruby
  * Similar to Java

## Class vs Module
* Classes are the blueprints for objects
  * Objects are instances of classes
* Modules are like classes but they cannot be instantiated
  * Modules are included or `mixed in` to other classes
  * When this is done, the class that mixed in the module can then use all of the
    methods in the module
* `Kernel` is a module in Ruby
* `Kernel` is mixed in to the `Object` class
  * So every object in Ruby has access to methods in the `Kernel` module
  * Examples include: print, puts, gets, exit

## Inheritance
* Inheritance in Ruby is specified using `<` in the class definition
* `class MyClass < SomeOtherClass`: MyClass inherits from SomeOtherClass
```ruby
class Hello
  def greeting()
    printf( "Hello!\n" )
  end
end

class GoodBye < Hello
  def farewell()
    printf( "Goodbye!\n" )
  end
end

greeter = Goodbye.new()
greeter.greeting()  # => Hello!
greeter.farewell()  # => Goodbye!
```
## Types of Variables
* Instance Variables
  * Referenced via an instance of a class
  * Prefixed by `@` in a class
* Class Variables
  * Shared among all instances of a Class
  * Like a static variable in Java
  * Prefixed by `@@`
  * Must be initialized before use
* Global Variables
  * Available globally to a program
  * Prefixed by `$`
* Constants
  * Declared either with either the first letter capitalized or all letters capitalized
  * Constants are always global scope
  * Constants are mutable in Ruby
