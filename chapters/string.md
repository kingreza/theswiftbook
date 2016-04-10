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

Swift's strings are bridgable to Foundation framework's `NSString` class indirectly. To load an instance of `String` from a file path URL, simply use the `String(contentsOfURL:)` initializer:

```swift
func readFromFile(url: NSURL){
  
  if let str = try? String(contentsOfURL: url){
    print(str)
  }
  
}
```

## Formatting

String formatting can easily be done inside the string object itself. Imagine that you have a constant called `age` of type `Int` and another constant called `name` of type `String`. You simply want to construct a string that says *"X is Y years old"* where X is the name and Y is the age. In this case you can use the `\()` formatting inside the string as shown here:

```swift
let age = 31
let name = "Foo"
let msg = "\(name) is \(age) years old"
//msg = "Foo is 31 years old"
```

## Converting

You can convert a String to different data types, such as `Int` or `UInt` using the destination data type's initializer:

```swift
let str = "123"
let int = Int(str)
let uint = UInt(str)
```

## Length

to be written

## Operators

to be written