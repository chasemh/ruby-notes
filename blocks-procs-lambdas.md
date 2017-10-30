# Ruby Blocks, Procs, Lambdas

## Block
* A block is a logical grouping of Ruby statements
* When a block is invoked in conjunction with a method, it is called a nameless function
* Blocks are commonly used in Ruby when iterating over a data structure, such as an Array or Hash.
* Blocks are placed in do/end blocks or curly braces {}
  * Note that do/end have lower precedence than {}
* Array Iteration Example
```ruby
arr = [ "A", "B", "C", "D", "E" ]
arr.each { |element|
  # element == The current element in the array
  printf( "%s ", element )  
}

# Alternate Format
arr.each do |element|
  printf( "%s ", element )
end
```

* A method can pass execution to a provided block using the `yield` keyword
* When `yield` is executed, execution moves to the beginning of the provided block. The block then executes and control comes back to the next statement in the method following the block.
* Yield Example
```ruby
def myMethod()
  if( block_given? )
    yield()
  else
    puts( "No block provided." )
end

myMethod() # => No block provided
myMethod(){ puts( "In the block!" ) } # => In the block!
```

* Blocks are closures (nameless functions or methods)

## Procs
* A proc is a procedure stored as a complete object
  * Basically a named block
* Can make a new proc with `Proc.new()` but preferred method is using the `lambda` or `proc` methods from `Kernel` as they do parameter checking
* Simple Proc Example:
```ruby
myBadProc = Proc.new{ puts( "I'm a proc made with Proc.new!" ) }
myLambda = lambda{ puts "I'm a lambda!" }
myGoodProc = proc{ puts "I'm a proc made with the proc method!" }

myBadProc.call()  # => I'm a proc made with Proc.new()!
myLambda.call()  # => I'm a lambda!
myGoodProc.call()  # =>I'm a proc made with the proc method!
```
* Procs are objects, blocks are not
* A method can have only one block as an argument. A method may have many procs as arguments.
* Lambdas and procs are similar but have some key differentiators
  * Lambdas check the number of arguments, Procs do not
  * When return is called in Lambda, execution returns to the line right after the lambda. When return is called in a proc, execution returns to the the code outside of the method where the proc is being executed.
* Arguments can be passed to blocks when `yield` or `call` is called
* Argument example
```ruby
# Regular Block Example
def myBlockMethod( x )
  yield( x )
end

myBlockMethod( 10 ){ |x|
  printf( "The block was passed %s.\n", x )
} # => The block was passed 10

# Lambda/Proc Example
def myMethod( myLambda )
  myLambda.call( 10 )
  myLambda.call( "Hello" )
end

myLambda = lambda{ |x| printf( "The lambda was passed %s.\n", x ) }
myMethod( myLambda ) # => The lambda was passed 10.
                     #    The lambda was passed Hello.
```
* Methods can convert blocks into procs.
  * To do this, the method must accept a proc argument, which is an argument prefixed with &
* Block to Proc Example
```ruby
def procToBlock( &myProc )
  yield()
  return myProc
end

myProc = procToBlock(){ puts "This is a block!" }
myProc.call() # => This is a block!
```
