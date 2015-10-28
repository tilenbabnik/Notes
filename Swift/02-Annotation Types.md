# Annotation Types

## Integers
Integers are whole numbers with no fractional component. They can either be signed (positive, zero, negative) or unsigned (postive, zero).

```swift
var wholeNumber = Int()
var hundred: Int = 100
var ten = 10

var binaryInteger = 0b10001 // 17 in binary notation (0b is a prefix)
var octalInteger = 0o21 // 17 in octal notation (0o is a prefix)
var hexadecimalInteger = 0x11 // 17 in hexadecimal notation (0x is a prefix)

var specialIntSyntax = 1_000_000 // using underscores for better code readability
```

## Floating Point Numbers
Floating-point numbers are numbers with a fractional component. Swift provides two signed floating-point number types.

### Double
Presents a 64-bit floating-point number. It is a preffered type. It's also inferred by default if Float is not specified explicitly.

### Float
Presents a 32-bit floating-point number.

```swift
var number = Double()
var someDouble: Double = 18.32817
var averageGrade = 8.5

var exponentDouble = 1.21875e1 // 12.1875 in exponent notation (e is suffix)
```

### Numeric Conversion
Conversion between integers and floating-point number types must be made explicit.

```swift
var three = 3
var pointOneFourOneFiveNine = 0.14159

let pi = Double(three) + pointOneFourOneFiveNine //pi equals 3.14159 and is of type double
let integerPi = Int(pi) // integerPi equals 3 and is of type int
```

## Booleans
Boolean values are referred to as logical, because they can only ever be true or false. Swift provides two Boolean constant values, true and false.

Boolean values are particularly useful in conditional statements such as if statements.

```swift
var permission = Bool()
var isAlive: Bool = true
var isLiked = false
```

## Strings
A string is an ordered collection of characters, such as "hello, world" or "albatross". Swift strings are represented by the String type, which in turn represents a collection of values of Character type.

```swift
var string = String()
var school: String = "MIT"
var sport = "Boxing"
```

### Initializing an Empty String
To create an empty String value as the starting point for building a longer string, either assign an empty string literal to a variable, or initialize a new String instance with initializer syntax.

Find out whether a String value is empty by checking its Boolean isEmpty property.

```swift
var emptyString = "" // Empty String literal
var anotherEmptyString = String() // initializer syntax

if emptyString.isEmpty {
    println("Nothing to see here") // Prints "Nothing to see here"
}
```

### Transforming Strings

```swift
println(welcome.uppercaseString) // Prints "HELLO THERE"
println(welcome.lowercaseString) // Prints "hello there"
```

### Concatenation and Interpolation
String values can be added together (or concatenated) with the addition operator (+) to create a new String value.

```swift
var greeting = "hello"
var pointer = " there"

var welcome = greeting + pointer // welcome equals "hello there"
```

You can also append a String value to an existing String variable with the addition assignment operator (+=).

```swift
var instruction = "look over"
instruction += pointer // instruction now equals "look over there")
```

You can append a Character value to a String variable with the String type’s append() method.

```swift
var exclamationMark: Character = "!"
welcome.append(exclamationMark) // welcome now equals "hello there!"
```

### String Interpolation
String interpolation is a way to construct a new String value from a mix of constants, variables, literals, and expressions by including their values inside a string literal. Each item that you insert into the string literal is wrapped in a pair of parentheses, prefixed by a backslash.

```swift
var multiplier = 3
var message = "\(multiplier) times 2.5 is \(Double(multiplier) * 2.5)" // "3 times 2.5 is 7.5"
```

### String Indexes
Use the startIndex property to access the position of the first Character of a String, and the endIndex property to access the posision of the last.

```swift
var streetGreeting = "Wassup"
println(streetGreeting.startIndex) // Prints "0"
println(streetGreeting.endIndex) // Prints "6"

streetGreeting[streetGreeting.startIndex] // "W"
streetGreeting[streetGreeting.startIndex.successor()] // "a"
streetGreeting[streetGreeting.endIndex.predecessor()] // "p"

// Accessing single character with advance() method
var index = advance(streetGreeting.startIndex, 4)
streetGreeting[index] // "u"

// Accessing all characters with indices() method
for index in indices(streetGreeting) {
    print("\(streetGreeting[index]) ")
} // Prints "W a s s u p"
```

### Inserting and Removing
To insert a character into a string at a specified index, use the insert(_:atIndex:) method.

```swift
streetGreeting.insert("!", atIndex: streetGreeting.endIndex) // streetGreeting is now "Wassup!"
```

To insert another string at a specified index, use the splice(_:atIndex:) method.

```swift
streetGreeting.splice(" dog", atIndex: streetGreeting.endIndex.predecessor()) // streetGreeting is now "Wassup dog!"
```

To remove a character from a string at a specified index, use the removeAtIndex(_:) method.

```swift
streetGreeting.removeAtIndex(streetGreeting.endIndex.predecessor()) // "!"
```

To remove a substring at a specified range, use the removeRange(_:) method.

```swift
var range = advance(streetGreeting.endIndex, -4)..<streetGreeting.endIndex // "6..<10"
streetGreeting.removeRange(range) // "Wassup"
```

### Comparing Strings
To check whether a string has a particular string prefix or suffix, call the string’s hasPrefix(_:) and hasSuffix(_:) methods, both of which take a single argument of type String and return a Boolean value.

You can use the hasPrefix(_:) method with the romeoAndJuliet array to count the number of scenes in Act 1 of the play.

```swift
var romeoAndJuliet = ["Act 1 Scene 1: Verona, A public place", "Act 1 Scene 2: Capulet's mansion", "Act 2 Scene 1: Outside Capulet's mansion"]
var act1SceneCount = 0

for scene in romeoAndJuliet { // Loops through romeoAndJuliet array
    if scene.hasPrefix("Act 1") { // Checks if it has a certain prefix and increments count
        ++act1SceneCount
    } // Executes two times
}

println("There are \(act1SceneCount) scenes in Act 1") // Prints "There are 2 scenes in Act 1"
```

Similarly, use the hasSuffix(_:) method to count the number of scenes that take place in or around Capulet’s mansion and Friar Lawrence’s cell.

```swift
var mansionCount = 0

for scene in romeoAndJuliet { // Loops through romeoAndJuliet array
    if scene.hasSuffix("Capulet's mansion") { // Checks if it has certain suffix
        ++mansionCount
    } // Executes two times
}

println("\(mansionCount) scenes happen in Capulet's mansion") // Prints "2 scenes happen in Capulet's mansion
```

### Converting Strings to Integers

```swift
var numberInString = "1234".toInt()
```

## Characters
You can access the individual Character values in a string by iterating over that string with a for-in loop.

```swift
var character = Character()
var firstChar: Character = "A"
var lastChar = "Z"

for character in "Dog! 🐶" {
    println(character)
} // Prints D, o, g, !, " ", 🐶
```

### Creating Strings from Characters Array

```swift
var catCharacters: [Character] = ["C", "a", "t", "!"," ", "😺"]
var catString = String(catCharacters)
println(catString) // Prints "Cat! 😺"
```

### Counting Characters
To retrieve a count of the Character values in a string, call the global count(_:) function and pass in a string as the function’s sole parameter.

```swift
var word = "restaurant"
println("There are \(count(word)) characters in word \(word)") // Prints "There are 10 characters in word restaurant"
```

## Tuple
Tuples group multiple values into a single compound value. The values within a tuple can be of any type and do not have to be of the same type as each other. Tuples are commonly used in return statements.

Tuples can later be decomposed into normal variables that can be accessed as usual.

```swift
var data = ("Urban", 20)
var http200status = (statusCode: 200, description: "OK")

var (name, age) = data // Decomposing tuple into two variables
println("\(name) is \(age) years old") // Prints "Urban is 20 years old"

// Accesing part of tuples can be done in both ways
println("The status code is \(http200status.0), that means it's \(http200status.1)") // Prints "The status code is 200, that means it's OK"

println("The status code is \(http200status.statusCode), that means it's \(http200status.description)") // Prints "The status code is 200, that means it's OK"
```

## Type Aliases
Type aliases define an alternative name for an existing type. You define type aliases with the typealias keyword.

```swift
typealias AudioSample = UInt16
var maxAmplitudeFound = AudioSample.min // maxAmplitudeFound is now 0
```