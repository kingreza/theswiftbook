# Integers

Integers are whole numbers which don't have a fractional component. For example, `0`, `1`, `2` and `-3` are integers, but `3.14` is not. Swift provides signed and unsigned integers with 8, 16, 32, and 64 bit forms. In addition to platform specific integers, such as `Int64` or `UInt32`, Swift has `Int`, `UInt` type to match automatically with the native word size of the current platform. In the most cases, it is helpful to use `Int` as the default integer type for consistency and interoperability excepting you specially need to dealt with specific integer types.

## [Syntax](#syntax)

Here is a simple way of creating an integer:

```swift
let testScore = 100
```

This creates a constant called `testScore` and assign a literal value of `100` to it. With [Swift type inference](data_types.md#type-inference), `testScore` is inferred to be of type `Int`. Also, You can declare variables and constants with explicit integer types.

```swift
var penalty: Int = -200
let bonus: UInt = 50  
```

In the above code, a variable called `penalty` is declared with `Int` type and a constant called `bonus` is declared with `UInt` type.
To improve code readability, you can use `_` between integers literals. For example :

```swift
let savingAccount = 1_000_000
print("savingAccount = \(savingAccount)")
// the result is `savingAccount = 1000000`  
```

## [Signed](#signed)

Signed integer can contain either zero, positive or negative values . You can use signed integer, such as `Int`or `Int64`, within their minimum and maximum range of value. You can use the `min` and `max` properties of both `UInt` and `Int` to determine the minimum and maximum values that these data types can hold, as shown here:

```swift
let maxValue: Int = Int.max // 1)
let maxValue32: Int32 = Int32.max // 2)
let maxValue64: Int64 = Int64.max  // 3)
```

On a 64-bit platform, `maxValue` is `9223372036854775807`, `maxVaue32` is `2147483647` and `maxValue64` is `9223372036854775807`. As mentioned in the beginning of this paragraph, the `Int` type has the same size as `Int64` on a 64-bit machine.  

## [Unsigned](#unsigned)

An unsigned integer can contain either the value zero or a positive value. To indicate an unsigned integer, you need the `U` character in front of integer types, such as `UInt`, `UInt32`. For example :

```swift
let familyMembers : UInt32 = 4
let clubMembers: UInt = 4
let zero = UInt.min // = 0
```

## [Converting](#converting)

TODO: write about converting integers to other types, such as strings, floats, double, etc

## [Operators](#operators)

TODO: write about default operators, such as +, -, +=, etc and talk about their priorities over each other and how we can use parenthesis to avoid confusion between operator priorities
