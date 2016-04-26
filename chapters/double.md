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

You can also be explicit about your data type by setting the type of your constants or variables direclty to `Double`, though this is excessive and completely unnecessary:

```swift
let value: Double = 123.456 //unnecessary data type declaration
value.dynamicType //Double.Type
```

## [Rounding](#rounding)

`Double` values, as mentioned previously, are made out of an exponent and a fraction. Sometimes you might wish to completely discard the fraction part of a `Double` value and keep the exponent. In that case, you can use the `round(_:)` function that is defined for `Double` as shown here:

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

Converting other types to `Double` is done through different initializers that `Double` provides you with, such as the following:

```swift
extension Double {
    public init?(_ text: String)
}
```

There are many more initializers for `Double` that can take a variety of different [data types](data_types.md) and turn them into `Double` as shown here:

```swift
let intValue = -123
let uintValue: UInt = 123
let floatValue: Float = 123.456
print(Double(intValue)) //"-123.0"
print(Double(uintValue)) //"123.0"
print(Double(floatValue)) //"123.456"
```

The initializer in `Double` that takes in a `String` and converts it to `Double` returns an [optional](optionals.md) `String` of type `String?`. The reason behind this is that not every `String` can be converted to `Double`. For instance:

```swift
let strValue = "123.456"
print(Double(strValue)) //"Optional(123.456)"

Double("Foo Bar") // = nil
```

If you want to grab the string value from the conversion, you need to learn about [optionals](optionals.md) in order to safely unwrap the optional value as shown here:

```swift
let strValue = "123.456"
if let value = Double(strValue){
  //value = 123.456
} else {
  //failed to convert the string to the double value
}
```

Should you wish to convert from `Double` to any other data type, use the destination type's initializer. Here are a few examples:

```swift
let double = 123.456
let int = Int(double) //123
let float = Float(double) //123.456
let string = String(double) //"123.456"
```

## [Operators](#operators)

Double has many different types of [operators](operators.md) already defined for it, such as `+`, `-` and `*`. All of these operators have different priorities so to avoid confusion as to which operator gets executed first in a complicated formula, use parenthesis to tell the compiler which equation has to be solved first. The rule is that the innermost parenthesis' value will be calculated first and cascade all the way out to the outermost parenthesis.

Here is an example of an equation that could be quite difficult to guess the result of:

```swift
let value1 = 1.2
let value2 = 2.3
let result = value1 + value2 / value1 + value2
```

You might assume that you could just resolve these values from left to right, so that we do the addition first, then the division and then the second addition. But this is not the case. What is happening here is that the division has the highest priority out of all the other operators, so first `value2` is being divided by `value1`, the result of which is `1.9166`. Then the compiler notices that there are only 2 operators left to resolve and those are both the `+` operator with the same priority so it resolves the rest of the equation from left to right, adding `value1` to `1.9166` to create `3.1166` and then adds `value2` to `3.1166` to create `5.4166`.

However, if you wish to do the operations in this order:

1. `value1 + value2`
2. Result of previous step divided by `value1`
3. Result of previous step added to `value2`

Then you can use parenthesis as shown here:

```swift
let value1 = 1.2
let value2 = 2.3
let result = ((value1 + value2) / value1) + value2
```

Since the innermost parenthesis gets resolved first, the compiler starts with `(value1 + value2)` and then divides the result of that by `value1` and then adds `value2` to the result of the previous step, as we wanted it to.

## [Useful Properties](#useful-properties)

The `Double` data type is [extendable](extensions.md) but by default has some very very important properties of its own, such as:

* `isInifinite`: that returns a `Bool` value if the current value placed inside the `Double` instance is infinity, as defined by [IEEE 754-1985 (positive and negative infinity definitions)](https://en.wikipedia.org/wiki/IEEE_754-1985#Positive_and_negative_infinity)
* `isNaN`: returns a `Bool` value indicating if the current `Double` value is Not a Number, or NaN as it is known as well. As defined by [IEEE 754-1985 (NaN definition)](https://en.wikipedia.org/wiki/IEEE_754-1985#NaN) again, Nan is:

> Some operations of floating-point arithmetic are invalid, such as dividing by zero or taking the square root of a negative number. The act of reaching an invalid result is called a floating-point exception. An exceptional result is represented by a special code called a NaN, for "Not a Number"

* `isZero`: as its name describes, returns a `Bool` value that is `true` if the given value is zero.
