# String

Strings in Swift, of type `String` hold characters. They can be in any language and they can even contain Emojis. `String` data type is a `struct` in Swift, therefore it is immutable. Should you wish to append to a string that you have already created, simply use the `+` operator.

## Syntax

Here is a simple way of creating a string:

```swift
let name = "Foo Bar"
```

This creates a constant called `name` and sets its value to a `String` that reads *"Foo Bar"*.

## Reversing

In order to reverse a string, simply call the `reverse()` function of the `characters` property of the string:

```swift
let name = "Foo Bar"
let reverse = String(name.characters.reverse())
```

The return value of this function is `ReverseCollection<Self>` so you need to type cast it to `String`.
## Mutating

`String` as a data type is defined as a `struct` in Swift, which by default renders it immutable. You can however use the `+` or the `+=` operators to append to an existing string, and create a new one that holds the existing string and the appended value. Here is an example:

```swift
var name = "Foo Bar"
name += " Baz"
name += " Qux"
```

Note how the string is defined as a `var`. You can also continue to use constants. Then for each new string you need a new constant as well:

```swift
let name = "Foo Bar"
let nameWithBaz = name + " Baz"
let nameWithQux = nameWithBaz + " Qux"
```

## Saving to and Loading From File

to be written

## Formatting

to be written

## Converting

to be written

## Length

to be written

## Operators

to be written