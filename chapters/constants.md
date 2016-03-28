# Constants

A constant is a storage place for *a value*, with a name and a type which can be implicitly or explicitly specified.

A constant's value cannot be changed after it has been created and named.

## Syntax

The `let` statement allows you to create a constant. What follows after `let` is the name of the constant that has to follow the [CamelCase naming convention](https://en.wikipedia.org/wiki/CamelCase).

Here is an example of a constant called *nameOfYourConstant* whose value is *xyz*. This constant has no explicit data type. Once you assign a value to a constant, Swift will figure out the data type automatically.

```swift
let nameOfYourConstant = xyz
```

If you want to explicitly assign a data type to a constant, use the following syntax:

```swift
let nameOfYourConstant: DataTypeOfYourConstant = xyz
```

Where `DataTypeOfYourConstant` is the data type.


## Why?

The biggest advantage of using a constant over a variable is that a constant's value cannot be changed after it is assigned. This creates the ease-of-mind feeling when writing code, that you know a constant's value will not be changed while you are working with it.

Constants and structures work hand in hand in creating highly parallelizable and thread-safe code where the objects are not mutated and are passed by value instead of reference.


## Implicitly Typed

Let's have a look at a few examples of creating constants.

* A constant named `value` with an implicit data type of `Int` with the value of `123`

```swift
let value = 123
```

## Explicitly Typed

To be written

## Conditional Initialization

To be written

## As Function Arguments

To be written





