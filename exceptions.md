# Ruby Exception Handling

* Can retry an exception block by using the `retry` keyword in a rescue statement

* Simple Exception Handling Prototype
```ruby
begin
  # Statements that could throw an exception
rescue
  # Statements for handling a thrown exception
ensure
  # Statements to always execute after the block ends
  # Executed following exception handling or no exception handling
end
```

* Multiple Exception Handling Prototype
```ruby
begin
  # Statements that could throw exceptions
rescue ExceptionTypeOne
  # Statements for handling an exception of type ExceptionTypeOne
rescue ExceptionTypeTwo
  # Statements for handling an exception of type ExceptionTypeTwo
else
  # Statements to execute if no exception is thrown
ensure
  # Statements to always execute after the block ends
  # Executed following exception handling or no exception handling
end
