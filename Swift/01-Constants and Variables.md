# Constants and Variables

## Declaring Constants and Variables
The value of a constant cannot be changed once it is set, whereas a variable can be set to a different value in the future. Variables can also be initialized empty however it doesn't make sense to do that with constant which cannot be later changed.

```swift
var dogname: String
var dogAge = Int()

let personName = "Luke" // personName is "Luke"
personName = "David" // compile-time error

var personAge = 15 // personAge is 15
personAge = 20 // personAge is now 20
```

Multiple constants or variables can be defined on one line like this.

```swift
var personBirthDay = 17, personBirthMonth = 7, personBirthYear = 1994
```

## Type Annotations
You can provide a type annotation when you declare a constant or variable, to be clear about the kind of values the constant or variable can store.

```swift
var welcomeMessage: String // welcomeMessage is of type String
welcomeMessage = "Hello" // welcomeMessage is "Hello"
```

Type annotations are not necessary. Multiple constants or variables can also be defined on one line like this.

```swift
var red, green, blue: Double
```

## Printing Constants and Variables
You can print the current value of a constant or variable with the println function. Use string interpolation to include variables in output string.

```swift
println(welcomeMessage) // Prints "Hello"
println("I'm \(personName) and I'm \(personAge) years old.") // I'm Luke and I'm 20 years old.
```

## Optionals
You use optionals in situations where a value may be absent. An optional says there is a value, and it equals x or there isn't a value at all.

You can use an if statement to find out whether an optional contains a value by comparing the optional against nil.

```swift
var dogName: String? // dogname is of type String?
dogName = "Fido" // we assigned a value of "Fifo"
dogName = nil // we can also not assign it any value

var possibleNumber = "123"
var convertedNumber = possibleNumber.toInt() // convertedNumber is of type int?

if convertedNumber != nil {
    println("convertedNumber has an integer value of \(convertedNumber!).")
} // Forced unwrapping with ! when we know for certain it has a value

// Following is a optional binding if statement.
if let actualNumber = possibleNumber.toInt() { // actualNumber is a constant name
    println("\(possibleNumber) has an integer value of \(actualNumber)")
} else {
    println("\(possibleNumber) could not be converted to an Integer.")
} // Prints "123 has an integer value of 123"
```