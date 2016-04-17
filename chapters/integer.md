# Integers

Integers are whole numbers which don't have a fractional component. For example, `0`, `1`, `2` and `-3` are integers, but `3.14` is not. Swift provides signed and unsigned integers with 8, 16, 32, and 64 bit forms. In addition to a platform specific integers, such as `Int64` or `UInt32`, Swift have `Int`, `UInt` type to match automatically with the native word size of the current platform. In the most cases, it is helpful to use `Int` as the default integer type for consistency and interoperability excepting you specially need to dealt with a specific integer types.

## Syntax

Here is a simple way of creating an integer:

```swift
let testScore = 100
```

This creates a constant called `testScore` and assign a literal value of `100` to it. With [Swift type inference](constants.md), `testScore` is inferred to be of type `Int`.

```swift
var penalty: Int = -200
let bonus: UInt = 50  
```

You can declare variables and constants with an explicit integer types. In the above code, a variable called `penalty` is declared with `Int` type and a constant called `bonus` is declared with `UInt` type.

## Signed

Signed integer can be a positive, negative integer and zero. As we mentioned in the above Integers section, use `Int` type will be enough unless you have to perform with a specific size of integers such as `Int32`.


## Unsigned

Unsigned integer can be a positive integer and zero. To indicate an unsigned integer, you need the `U` character in front of integer types, such as `UInt`, `UInt32`. For example :

```swift
let familyMembers : UInt32 = 4
let clubMembers: UInt = 4
```

## Converting

to be written

## Operators

to be written
