# Ruby Strings

* Strings are sequences of characters
* Can declare a string using single or double quotes
  * Double quotes interpret escaped characters
  * Single quotes preserve escaped characters
* Mutable in Ruby, unlike Java
  * Use `.freeze()` to make the string immutable

## General Delimited Strings
* Not declared with quotes
* Preceded by `%` and then followed by a matched pair of delimiter characters, such as `!`, `{}`, `()`, `[]` etc.
  * Must be nonalphanumeric
* String embedded between delimiters
* Example
```ruby
myString = %!This is the string!
anotherString = %{This is another string}
```

## Here Documents
* Allow you to build strings from multiple lines while preserving newlines
* Example
```ruby
myString = <<EOF
Some words
Some more words
Even more words
EOF
```

## Concatenation
* Can concatenate strings together using `+`, `<<`, `.concat`
* Example:
```ruby
s1 = "Hello "
s2 = "World"
s1 + s2  # => Hello World
s1 <<  s2 # => Hello World
s1.concat( s2 ) # => Hello World
```

## Comparing
* `==`: Can be used to compare two String objects. Returns true if they are exactly the same in length and content
* `.eql?()`: Behaves like `==`. Actually used by `==`.
* `<=>`: Spaceship Operator. Compares the character codes of strings.
* `casecmp( anotherString)`: Compares strings, ignoring case differences.

## Manipulation
* Can insert another string into a string using the `insert( index, string )` method
* Can alter parts of a string using []= ( slice!() )
* Example
```ruby
s = "Hello World!"
s[ "Hello" ]= "Goodbye"
puts( s )  # => Goodbye World
```

## Chomp and Chop
* `chop`: Removes the last character of a string
* `chomp`: Removes a record separator from a string

## Delete
* `gsub`: Allows you to delete characters in a string
* Deletes all occurrences of the string to delete
* Delete uses the intersection ( what is the same in both ) to decide which pieces of the string to delete
* Can use a caret (^) to negate part of an arguments
* Example
```ruby
 "hello world".delete( "abcdefghijklmnopqrstuvwxyz", "^he" ) # => "he "
```

## Substring substitution
* `gsub`: Replaces the given substring with a replacement string
* Example
```ruby
"Hello World".gsub( "Hello", "Goodbye" )  # => Goodbye World
```
* `replace`: Completely replaces the content of the calling string with a given string
  * Why do this?: Keeps the ID of the calling string the same

## Reverse
* `reverse`: Reverses a given string

## String to Array
* Use `split( delimiter )` to split a string in an array based upon the given delimiter

## Case conversion
* `capitalize`: Capitalize first word
* `upcase`: Uppercase everything
* `downcase`: Lowercase everything
* `swapcase`: Swap the case of every character

## Iteration
* Can use `.each` method to iterate over every character in a string

## Manipulating Whitespace
* `ljust( spaces, spacingCharacter )`: Left justify string by given amount of spaces. Must be equal to or longer than the calling string.
* `rjust( spaces, spacingCharacter )`: Right justify string by given amount of spaces. Must be equal to or longer than the calling string.
* `center( spaces, spacingCharacter )`: Centers text
* `lstrip`: Strip whitespace from left side of string
* `rstrip`: Strip whitespace from right side of string
* `strip`: Strip whitespace from both sides of string

## Incrementing
* Strings can be "incremented" using the `next` or `succ` methods
* `next` always increments the rightmost character
* When a boundary is hit (z), an additional digit is added
  * Ex. `"z".next() # => "aa"`
* Works for any character set
* Can also be used to increment numbers in strings

## Conversions
* Can convert strings into floats, integers using `to_f` and `to_i` respectively
* Can convert floats and integers into strings using `to_s`
* Use `intern` or `to_sym` to convert a string to a symbol

## Regular Expressions
* Can search strings using regular expressions and the grep method from the enumerable module.
* 
