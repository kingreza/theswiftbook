# Mutating a Structure

TODO: talk about the fact that the `mutating` syntax can allow a function inside a struct to mutate the structure and tell the reader what this actually means. does it create a new struct or does it use the existing struct

## [Avoidance](#avoidance)

TODO: tell the reader why mutating in general is not a good idea and how they can instead create functions that return a new structure with the new values

## [Through Variables](#through-variables)

TODO: tell the reader how a variable can mutate a structure

## [Through Functions](#through-functions)

TODO: give examples of how a `mutating func` can be created

## [In a Function](#in-a-function)

TODO: talk about how when a structure is passed to a function, it cannot be mutated unless it is defined as `inout` or it is assigned to a variable inside the function at which point a new copy of the struct will be created

