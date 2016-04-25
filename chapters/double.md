# Double

The data type `Double` can represent a double precision floating number, that is similar to `Float`, but has more precision over its exponent and fraction values where:

* Exponent: so to speak, is the number that appears behind the dot (e.g. in 123.456, exponent is 123)
* Fraction: is the number after the dot (456 in the previous example)

By default, a number with a fraction in Swift is of type `Double`, unless specified otherwise explicitly by the programmer.

## [Syntax](#syntax)

Using Swift's [Type Inference](data_types.md#type-inference), you can create an instance of `Double` simply by placing a floating number inside a constant or a variable:

```swift
let value = 123.456
value.dynamicType //Double.Type
```

You can also be explicit about your data type by setting the type of your constant or variables direclty to `Double`, though this is excessive and completely unnecessary:

```swift
let value: Double = 123.456 //unnecessary data type declaration
value.dynamicType //Double.Type
```

## [Rounding](#rounding)

`Double` values, as mentioned previously, are made out of an exponent and a fraction. Sometimes you might wish to completely discard the fraction part of a Double value and keep the exponent. In that case, you can use the `round(_:)` function that is defined for `Double` as shown here:

```swift
@warn_unused_result
public func round(x: Double) -> Double
```

As you can see, both the argument and the return value of this function are of type `Double`. Here is an example where you can use this function to remove the fraction of a `Double` value and only keep the exponent:

```swift
let value = 123.456
let oneTwoThree = round(value) // = 123
```

## [Converting](#converting)

TODO: write about converting double to CGFloat and Int and UInt or even String

## [Operators](#operators)

TODO: write about the default operators that can be applied to Double such as +, -, etc. And write about their priorities and using parenthesis to avoid confusion

## [Useful Properties](#useful-properties)
TODO: explain properties like `isInfinite`, `isNaN` and `isFinite`
