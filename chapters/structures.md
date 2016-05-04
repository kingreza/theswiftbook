# Structures

Structures and Classes make up the building blocks of your code. We are going to start with Structures, their syntax and general purpose. Then we will highlight how they are like Classes and then we will at look what makes them different

Structures, much like Classes can hold your variables and functions. In Swift, defining a new Structure is simple. 

## [Syntax](#syntax)
````Swift
struct Person {
  
}
````
As mentioned earlier, Structures, much like classes can have properties that will store values.

````Swift
struct Person {
  var name: String = "John Doe"
}
````
They can also have methods that add functionality to the the Strutucture.

````Swift
struct Person {
  var name: String = "John Doe"

  func printName() {
    print(self.name)
  }
}
````
Like Classes Strucutres can also have initializers that set up their initial state.

````Swift
struct Person {
  var name: String = "John Doe"
  var favoriteMovies: [String]
  
  init(favoriteMovies: [String])
  {
    self.favoriteMovies = favoriteMovies
  }
  
  func printName() {
    print(self.name)
  }
}
````

In Swift, strucdtures like classes can extending, we will cover this in more details 

TODO: just give a few examples of how a structure can be created and even create them from different protocols perhpas and then link to protocols

## [Versus Classes](#versus-classes)

TODO: talk about how structures are different from classes and give examples

