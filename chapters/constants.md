# Constants

A constant is a storage place for *a value*, with a name and a type which can be implicitly or explicitly specified.

A constant's value cannot be changed after it has been created and named.

## [Syntax](#syntax)

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


## [Why](#why)

The biggest advantage of using a constant over a variable is that a constant's value cannot be changed after it is assigned. This creates the ease-of-mind feeling when writing code, that you know a constant's value will not be changed while you are working with it.

Constants and structures work hand in hand in creating highly parallelizable and thread-safe code where the objects are not mutated and are passed by value instead of reference.


## [Implicitly Typed](#implicitly-typed)

A constant can be created simply with the following input to the Swift compiler:

1. The `let` statement
2. The name of the constant
3. A value

In Swift, you don't have to explicitly set the data type of your constants or your variables. The compiler derives this information from the value that you assign to the constant or the variable.

Here is a constant named `value` with an implicit data type of `Int` with the value of `123`

```swift
let value = 123
```

Here is another constant named `person` with the implicit data type of `String`:

```swift
let person = "Foo Bar"
```

## [Explicitly Typed](#explicitly-typed)

If you want to explicitly define the data type of a constant, you can do that by attaching `:X` to the end of the constant name, where `X` is the data type, such as:

* `Int`
* `String`
* `Double`

Here is an example of a constant whose data type is explicitly set to `String`:

```swift
let person: String = "Foo Bar"
```

It is not a good idea to set the data type explicitly, as it is extra job that has no advantage, unless in very specific situations. For instance, imagine that you have the following enumeration:

```swift
enum Direction{
  case Left, Right, Down, Up
}
```

Some programmers prefer to create an instance of this enumeration using the following syntax:

```swift
let up = Direction.Up
```

And some prefer to set the data type explicitly so that they can take advantage of the shorthand for enumeration cases:

```swift
let up: Direction = .Up
```

## [Conditional Initialization](#conditional-initialization)

TODO: write about how we can create a constant that doesn't have an initial value and how we can set this value conditionally with if statements later before use






