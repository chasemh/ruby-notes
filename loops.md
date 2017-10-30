# Ruby Loops

* Like most languages, a program can break out of a loop by using the `break` keyword
* Go the next iteration of a loop with `next`
* Redo the current iteration of a loop with `redo`
* Restart an entire loop with `retry`

## While Loops
* Executes while loop condition is true
* Prototype:
```ruby
while( condition )
  # Stuff to do while condition is true
end
```
* Array while loop example
```ruby
arr = [ 1, 2, 3, 4, 5 ]
i = 0

# Loops while arr[ i ] is true
# That is, while there are still elements remaining in the array
while arr[ i ]
    puts( arr[ i ] )
    i += 1
end
```

### Using while as a modifier
* Sort of like a do-while loop in Java
* Prototype:
```ruby
stuffToDo while( condition )
```

```ruby
arr = [ 1, 2, 3, 4, 5 ]
i = 0;

begin
  puts( arr[ i ] )
  i += 1
end while( arr[ i ] )
```

## Until Loop
* Like a while loop, but executed while the conditional is false
* Prototype
```ruby
begin
  # Statements to execute while conditional is false
end until( conditional )
```

## loop Method
* `Kernel` module contains a method called `loop`
* This method executes continuously until `break` is called
* Prototype
```ruby
loop do
  # Statements to execute
  break if conditional
end
```

## For Loop
* Loops over a given range, incrementing the counter each time
* Prototype
```ruby
for i in 1..5
  printf( "%d ", i )
end
```
* Note `a..b` designates an inclusive range from a to b (b is included) and `a...b` designates an exclusive range from a to b (b is not included)

## Times "Loop"
* Ruby Integer class has a `times()` method. When a block is passed to the method, it will be executed the same number of times as the value of the calling object
  * i.e. `10.times{ statements }` would execute 10 times
* If the block passed to time accepts an argument, the value of the argument for the Nth iteration will be N, where N is between 0 and the value of the calling integer
  * i.e. `10.times { |i | print( i, " ") } # => 0 1 2 3 4 5 6 7 8 9`

## upto Method
* Behaves similarly to a for loop but is more concise
* Integer, String and Data classes have `upto` methods
* Example
```ruby
1.upto( 10 ){ |i| printf( "%d ", i ) } # => 1 2 3 4 5 6 7 8 9 10
```
## downto Method
* Like `upto` but counts down from a certain point
* Example
```ruby
5.downto(1) { |i| printf( "%d ", i ) } # => 5 4 3 2 1
```
