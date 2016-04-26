# Optional Chaining

Optional chaining in Swift allows nested optional values to be extracted and read only if their parents are valid instances of an object.

Imagine the following data structure:

```swift
struct Name{
  let value: String?
}

struct Person{
  let name: Name?
}
```

A `Person` structure has an optional property called `name` of type `Name` and the `Name` structure has an optional `value` property that holds a person's name essentially.

Now you are tasked with writing a function called `processNameFor(_:)` that takes in an optional instance of `Person` (as in `Person?`), and does some work with that person's name.

In order for this function to access the underlying `value` of the name of the optional person, it has to unwrap the optional values all the way down to `value` as shown here:

```swift
func processNameFor(person: Person?){
  
  guard let person = person,
    let name = person.name,
    let str = name.value
    where str.characters.count > 10 else{
    return
  }
  
  //now we have access to str that is the actual name of a person
  
}
```

This can easily get quite cumbersome to type and difficult understand. The solution to this is using Swift's optional chaining capabilities to read the `value` field of the `name` property of the `Person` instance only if the person exist and has a valid `Name` instance set for it.

## [Usage](#usage)

You can use the `?` optional unwrapper at the end of every optional value in order to access a property or a function of that value, only if the value itself is backed by a real instance of the type, and not `nil`.

So we can replace the previous example with the following:

```swift
func processNameFor(person: Person?){
  
  guard let name = person?.name?.value
    where name.characters.count > 10 else {
    return
  }
  
  //now we have access to str that is the actual name of a person
  
}
```

Where:
* `person?`: optionally gives us access to all its properties and functions should the `person` argument itself be a valid instance of the `Person` structure.
* `name?`: optionally gives us access to all properties and functions of the `Name` structure should both person and its name be valid instances of `Person` and `Name` in that order.

The general syntax for optional chaining is:

```swift
let someOptionalValue = optional1?.optional2?.optional3
```

## [In Dictionaries](#in-dictionaries)

The type [`Dictionary`](dictionary.md) in Swift has a useful subscript that allows you to read the value of a given key:

```swift
/// Access the value associated with the given key.
///
/// Reading a key that is not present in `self` yields `nil`.
/// Writing `nil` as the value for a given key erases that key from
/// `self`.
public subscript (key: Key) -> Value?
```

This method however returns an optional value. This means that if you have a nested dictionary, as usually is the case for [JSON](http://www.json.org/) documents, you will be able to use optional chaining to unwrap a nested series of dictionary keys until you arrive at the value that you are looking for.

Imagine the following dictionary:

```swift
let dict = [
  "key1" : [
    "key1.1" : [
      "key1.1.1" : "value1.1.1",
      "key1.1.2" : "value1.1.2"
    ],
    "key1.2" : [
      "key1.2.1" : "value1.2.1",
      "key1.2.2" : "value1.2.2",
    ]
  ],
  "key2" : [
    "key2.1" : [
      "key2.1.1" : "value2.1.1",
      "key2.1.2" : "value2.1.2",
    ],
    "key2.2" : [
      "key2.2.1" : "value2.2.1",
      "key2.2.2" : "value2.2.2",
    ]
  ]
]
```

Now let's say that you want to read the value of `key2.2.2`. Traditionally, you would be able to, one by one, unwrap the keys and their values until you arrive at your destination like so:

```swift
if let keyTwoValues = dict["key2"],
  keyTwoPointTwo = keyTwoValues["key2.2"],
  keyOnePointTwoPointTwo = keyTwoPointTwo["key2.2.2"]{
  keyOnePointTwoPointTwo // = "value2.2.2"
}
```

Instead of this complicated code, you can however use optional chaining to read the value of the `key2.2.2` key:

```swift
if let valueTwoPointTwoPointTwo = dict["key2"]?["key2.2"]?["key2.2.2"]{
  valueTwoPointTwoPointTwo // = "value2.2.2"
}
```
