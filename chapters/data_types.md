# Data Types

Whenever a value is defined in Swift, either implicitly or explicitly, it gets a type, known as a data type.

A few main data types that you can use in Swift are:

| Data Type | What does it represent? |
| -- | -- |
| [`Int`](integer.md) | An integer, that can be either signed or unsigned, meaning that it can either be positive or negative. |
| [`String`](string.md) | Text, such as *"Hello, World"* |
| [`Double`](double.md) | A value with fraction, such as *1.22* or *123.98* |

In this section of The Swift Book you will learn about some of the most important and built-in data types that are used in almost every Swift project that you might be able to get your hands on.

## [Type Inference](#type-inference)

Swift doesn't require the programmer to define an explicit data type for values stored in [constants](constants.md) or [variables](variables.md). When you specify a value of `"Hello, World"` to a constant, Swift deducts from the value that the type should be `String`. Here are a few examples:

```swift
let age = 31 //Int
let name = "Foo" //String
let value = 20.1 //Double
let negativeValue = -20 //Int
```

Here are the rules that Swift follows in order to set implicit data types on constants and variables:

* Values enclosed in quotation marks are of type `String`
* Values without a fraction are of type `Int`
* Values with a fraction are of type `Double`

You can of course override the detected data type by explicitly specifying your data types on your constants and variables, as shown here:

```swift
let age: UInt = 31
let value: CGFloat = 20.1
```
