# Structures

Structures and Classes make up the building blocks of your code. We are going to start with Structures, their syntax and general purpose. Then we will highlight how they are like Classes and then finish with what makes them different

In Swift, defining a new Structure is simple. 

## [Syntax](#syntax)
````Swift
struct Person {
  
}
````
Structures, much like Classes can have properties that will store values.

````Swift
struct Person {
  var name: String = "John Doe"
}
````
They can also have methods that add functionality to the Structure.

````Swift
struct Person {
  var name: String = "John Doe"

  func printName() {
    print(self.name)
  }
}
````
Like Classes, Structures can also have initializers that set up their initial state.

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
In Swift, Structures like classes can also be extended. Assuming the structure defined aboved exists somewhere in our project we can extend its functionality, just as we can in Classes somewhere else in our code 

````Swift
extension Person {
  func printFavoriteMovies() {
    for movie in favoriteMovies {
      print(movie)
    }
  }
}
````

Strucutres, like Classes 

TODO: just give a few examples of how a structure can be created and even credate them from different protocols perhpas and then link to protocols

## [Versus Classes](#versus-classes)

TODO: talk about how structures are different from classes and give examples

