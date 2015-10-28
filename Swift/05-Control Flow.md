# Control Flow

## For Loop

```swift
for var index = 0; index < 3; ++index {
    println("Index is \(index)")
} // Prints "Index is 0", "Index is 1", "Index is 2"

// To be able to access incremented variable declare it before loop
var index: Int
for index = 0; index < 3; ++index {
    println("index is \(index)")
} // Prints same as before

println("The loop statements were executed \(index) times") // Prints "The loop statements were executed 3 times"
```

## For In Loop

```swift
// Use it to iterate over a sequence
for index in 1...5 {
    println("\(index) times 5 is \(index * 5)")
} // Prints "1 times 5 is 5", "2 times 5 is 10", ..., "5 times 5 is 25"

var base = 3
var power = 10
var answer = 1

for _ in 1...power {
    answer *= base
}
print("\(base) to the power of \(power) is \(answer))") // Prints "3 to the power of 10 is 59049"

// Use it to iterate through an array
var names = ["James", "Anna", "Alex"]
for name in names {
    print("Hello, \(name)")
} // Prints "Hello, James", "Hello, Anna", "Hello, Alex"

// Or a dictionary
var numberOfLegs = ["Spider": 8, "Ant": 6, "Cow": 4]
for (animal, legCount) in numberOfLegs {
    println("\(animal) has \(legCount) legs.")
} // Prints "Spider has 8 legs.", "Ant has 6 legs.", "Cow has 4 legs."
```

## While Loop

```swift
import UIKit // Needed for random number

// Creation of game board
let finalSquare = 25
var board = [Int](count: finalSquare + 1, repeatedValue: 0)
var square = 0

// Ladders
board[03] = +08; board[06] = +11; board[09] = +09; board[10] = +02

// Snakes
board[14] = -10; board[19] = -11; board[22] = -02; board[24] = -08
board

while square < finalSquare {
    print("Start position: \(square)")
    var diceRoll = Int(arc4random_uniform(6)) + 1 // roll the dice
    print(" Dice roll: \(diceRoll)")
    square += diceRoll // move by the rolled amount
    print(" After move position: \(square)")
    if square < board.count { // if we're still on the board
        println(" Special move: \(board[square])")
        square += board[square] // move down or up for a snake or a ladder
    }
}
println("\nGame is over!")
```

## Do While Loop

```swift
do {
    print("Start position: \(square)")
    var diceRoll = Int(arc4random_uniform(6)) + 1 // roll the dice
    print(" Dice roll: \(diceRoll)")
    square += diceRoll // move by the rolled amount
    print(" After move position: \(square)")
    if square < board.count { // if we're still on the board
        println(" Special move: \(board[square])")
        square += board[square] // move down or up for a snake or a ladder
    }
} while square < finalSquare
println("\nGame is over!")
```

## If Statement

```swift
var temperature = 5

if temperature < 10 {
    println("It's very cold.")
} // Prints "It's very cold."

temperature = 20 // temperature is now 20

if temperature < 10 {
    println("It's very cold.")
} else {
    println("It's not cold. Wear a t-shirt.")
} // Prints "It's not cold. Wear a t-shirt."
```

## Switch Statement

```swift
var someCharacter: Character = "e"

switch someCharacter { // switches someCharacter against cases with multiple values
case "a", "e", "i", "o", "u":
    println("\(someCharacter) is a vowel")
case "b", "c", "d", "f", "g", "h", "j", "k", "l", "m", "n", "p", "q", "r", "s", "t", "v", "w", "x", "y", "z":
    println("\(someCharacter) is a consonant")
default:
    println("\(someCharacter) is not a vowel or a consonant")
} // Prints "e is a vowel"
```

### Switching with intervals

```swift
var count = 3_000_000_000_000
var naturalCount: String

switch count { // switches count against cases with intervals
case 0:
    naturalCount = "no"
case 1...3:
    naturalCount = "a few"
case 4...9:
    naturalCount = "several"
case 10...99:
    naturalCount = "tens of"
case 100...999:
    naturalCount = "hundreds of"
case 1000...999_999:
    naturalCount = "thousands of"
default:
    naturalCount = "millions and millions of"
}
println("There are \(naturalCount) stars in the Milky Way.") // Prints "There are millions and millions of stars in the Milky Way."
```

### Switching with tuples

```swift
var somePoint = (0, 0)

switch somePoint { // switches both values of somePoint
case (0, 0):
    println("Point (0, 0) is at the origin.")
case (_, 0):
    println("Point (\(somePoint.0), 0) is on the x-axis")
case (0, _):
    println("Point (0, \(somePoint.1)) is on the y-axis")
case (-2...2, -2...2):
    println("Point (\(somePoint.0), \(somePoint.1)) is inside the box")
default:
    println("Point (\(somePoint.0), \(somePoint.1)) is outside the box")
} // Prints "Point (0, 0) is at the origin."
```

### Value Bindings

```swift
var anotherPoint = (2, 0)

switch anotherPoint {
case (let x, 0):
    println("on the x-axis with an x value of \(x)")
case (0, let y):
    println("on the y-axis with an y value of \(y)")
case (let x, let y):
    println("somewhere else at (\(x), \(y))")
} // Prints "on the x-axis with an x value of 2"
```

### Where Clause

```swift
var yetAnotherPoint = (1, -1)

switch yetAnotherPoint {
case let (x, y) where y == x:
    println("(\(x), \(y)) is on the line y = x")
case let (x, y) where y == -x:
    println("(\(x), \(y)) is on the line y = -x")
case let (x, y):
    println("(\(x), \(y)) is just some arbitrary point")
} // Prints "(1, -1) is on the line y = -x"
```

## Control Transfer Statements

### Continue
Continue breaks out of current iteration and continues the loop.

```swift
var puzzleInput = "great minds think alike"
var puzzleOutput = ""

for character in puzzleInput { // Iterates over a string for characters
    switch character { // Switches current character
    case "a", "e", "i", "o", "u", "u", " ":
        continue // tells a loop to stop and go to next iteration
    default:
        puzzleOutput.append(character)
    }
}
println(puzzleOutput) // Prints "grtmndsthnklk"
```

### Break
Break completely exits the loop and no more code is ran. It can also be used for default statement in switch statements.

```swift
for number in 1...20 { // Iterates through numbers 1 - 20
    if number % 2 == 0 {
        println("even")
    }
    if number % 2 == 1 {
        println("odd") // Prints "1" when number = 1
        break // break statement that says to stop the loop, so nothing else get's called
    }
    if number % 5 == 0 {
        println("multiple of five")
    }
    if number % 10 == 0 {
        println("multiple of 10")
    }
}

var personName = "Russell"

switch personName {
case "Jack":
    println("It's Jack!")
case "Russell":
    println("It's Russell!")
default:
    break // when we don't want to do anything in default statement just insert break
} // Prints "It's Russell!
```

### Fallthrough

```swift
var integerToDescribe = 5
var description = "The number \(integerToDescribe) is"

switch integerToDescribe {
case 2, 3, 5, 7, 11, 13, 17, 19:
    description += " a prime number and also"
    fallthrough // says to execute the next case also
default:
    description += " an integer."
}
println(description) // Prints "The number 5 is a prime number and also an integer.
```

## Labeled Statements

```swift
var dogAge = 0

dogAgeLoop: while dogAge < 15 {
  switch dogAge {
    case 10:
      println("She's 10")
      break dogAgeLoop
    default:
      dogAge += 1
  }
}
```