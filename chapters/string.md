# String

Strings in Swift, of type `String` hold characters. They can be in any language and they can even contain Emojis. `String` data type is a `struct` in Swift, therefore it is value type, meaning that when it is passed to a function, it will be copied rather than passed as a reference. Should you wish to append to a string that you have already created, simply use the `+` operator.

## [Syntax](#syntax)

Here is a simple way of creating a string:

```swift
let name = "Foo Bar"
```

This creates a constant called `name` and sets its value to a `String` that reads *"Foo Bar"*.

## [Reversing](#reversing)

In order to reverse a string, simply call the `reverse()` function of the `characters` property of the string:

```swift
let name = "Foo Bar"
let reverse = String(name.characters.reverse())
```

The return value of this function is `ReverseCollection<Self>` so you need to type cast it to `String`.

## [Mutating](#mutating)

`String` as a data type is defined as a `struct` in Swift, and has mutating functions. You can use the `+` or the `+=` operators to append to an existing string, and create a new one that holds the existing string and the appended value. Here is an example:

```swift
var name = "Foo Bar"
name += " Baz"
name += " Qux"
```

There are mutable functions, as mentioned before, on String. To use those, you need to define your string object as a [variable](variables.md). Here is an example that allows you to use the `write(_:)` mutating function on `String` to append a string to your current variable:

```swift
var name = "Foo"
name.write(" Bar")
//name = "Foo Bar"
```

Note how the string is defined as a `var`. You can also continue to use constants. Then for each new string you need a new constant as well:

```swift
let name = "Foo Bar"
let nameWithBaz = name + " Baz"
let nameWithQux = nameWithBaz + " Qux"
```

## [Saving to and Loading From File](#saving-to-and-loading-from-file)

Swift's strings are bridgable to Foundation framework's `NSString` class indirectly. To load an instance of `String` from a file path URL, simply use the `String(contentsOfURL:)` initializer:

```swift
func readFromFile(url: NSURL){

  if let str = try? String(contentsOfURL: url){
    print(str)
  }

}
```

## [Formatting](#formatting)

String formatting can easily be done inside the string object itself. Imagine that you have a constant called `age` of type `Int` and another constant called `name` of type `String`. You simply want to construct a string that says *"X is Y years old"* where X is the name and Y is the age. In this case you can use the `\()` formatting inside the string as shown here:

```swift
let age = 31
let name = "Foo"
let msg = "\(name) is \(age) years old"
//msg = "Foo is 31 years old"
```

## [Converting](#converting)

You can convert a String to different data types, such as `Int` or `UInt` using the destination data type's initializer:

```swift
let str = "123"
let int = Int(str)
let uint = UInt(str)
```

## [Length](#length)

Get the length of a string using the `count` property of the `characters` property of the string:

```swift
let length = "Hello".characters.count
```

You can also get the UTF-8 length of a string using the `utf8.count` property of the string:

```swift
let length = "Hello".utf8.count
```

Strings have different representations that you can access with various properties, namely `utf8` and `utf16`.

## [Operators](#operators)

to be written
