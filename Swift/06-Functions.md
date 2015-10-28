# Functions

## Defining and Calling Functions

```swift
func sayHello(personName: String) -> String { // One parameter personName is of type String
    let greeting = "Hello, " + personName + "!"
    return greeting // Returns greeting of type String
}

println(sayHello("Anna")) // Prints "Hello, Anna!"
println(sayHello("Brian")) // Prints "Hello, Brian!"
```

## Parameters

### Multiple Input Parameters

```swift
func halfOpenRangeLength(start: Int, end: Int) -> Int { // Two parameters start, end both of type Int
    return end - start // Returns end - start which is of type Int
}

println(halfOpenRangeLength(1, 10)) // Prints "9"
```

### Functions Without Parameters

```swift
func sayHelloWorld() -> String { // No parameters
    return "Hello, world!" // Returns a String
}

println(sayHelloWorld()) // Prints "Hello, world!"
```

### Variadic Parameters

```swift
func arithmeticMean(numbers: Double...) -> Double { // Parameter is an array numbers of type Double with no defined number of elements
    var total: Double = 0
    for number in numbers {
        total += number
    }
    return total / Double(numbers.count) // Returns a Double
}

arithmeticMean(1, 2, 3, 4, 5, 6, 7) // Returns "4.0"
arithmeticMean(3, 8.25, 18.75) // Returns "10.0"
```

### Parameters as Variables

```swift
func alignRight(var string: String, howMuch: Int, pad: Character) -> String { // When not specified parameters are constants, however if var is put in front of parameter name a copy of argument will be made
    let amountToPad = howMuch - count(string)
    if amountToPad < 1 {
        return string
    }
    let padString = String(pad)
    for _ in 1...amountToPad {
        string = padString + string
    }
    return string
}
let originalString = "Hello"
let paddedString = alignRight(originalString, 10, "-") // paddedString is equal to "-----Hello"
// originalString is still equal to "Hello" because when passed as a parameter a copy has been made
```

### In-Out Parameters

```swift
func swapTwoInts(inout a: Int, inout b: Int) { // When we want to change original argument put inout before parameter name
    let temporaryA = a
    a = b
    b = temporaryA
}

var someInt = 3
var anotherInt = 107
swapTwoInts(&someInt, &anotherInt)
println("someInt is now \(someInt), and anotherInt is now \(anotherInt)") // Prints "someInt is now 107, and anotherInt is now 3"
```

### Default Parameter Values

```swift
func joinModified(string s1: String, toString s2: String, withJoiner joiner: String = " ") -> String { // sets the default value for joiner as " "
    return s1 + joiner + s2
}

// If withJoiner is provided the function will use it.
joinModified(string: "Hello", toString: "World", withJoiner: "-") // Returns "Hello-World"

// However if withJoiner is not provided the default value " " will be used
joinModified(string: "Hello", toString: "World") // Returns "Hello World"
```

## Return Values

### No Return Values

```swift
func sayGoodbye(personName: String) { // One parameter personName of type String
    println("Goodbye, \(personName)!")
} // Doesn't return anything, just executes code inside.

sayGoodbye("Dave") // Prints "Goodbye, Dave!"
```

### Multiple Return Values

```swift
func sayGoodbye(personName: String) { // One parameter personName of type String
    println("Goodbye, \(personName)!")
} // Doesn't return anything, just executes code inside.

sayGoodbye("Dave") // Prints "Goodbye, Dave!"
```

### Optional Tuple Return Types

```swift
func minMaxModified(array: [Int]) -> (min: Int, max: Int)? {
    if array.isEmpty { return nil } // If array is empty function will return nill and will not perform the following code.
    var currentMin = array[0]
    var currentMax = array[0]
    for value in array[1..<array.count] {
        if value < currentMin {
            currentMin = value
        } else if value > currentMax {
            currentMax = value
        }
    }
    return (currentMin, currentMax) // Returns a tuple of type (Int, Int)
}

if let anotherBounds = minMaxModified([8, -6, 2, 109, 3, 71]) {
    println("Min is \(bounds.min) and Max is \(bounds.max).")
} // Prints "Min is -6 and Max is 109."
```

## Parameter Names

### External Parameter Names

```swift
func join(string s1: String, toString s2: String, withJoiner joiner: String) -> String { // External names are string, toString, withJoiner
    return s1 + joiner + s2 // Returns a String
}

join(string: "Hello", toString: "World", withJoiner: ", ") // Returns "Hello, World"
```

### Shorthand External Parameter Names

```swift
func containsCharacter(#string: String, #characterToFind: Character) -> Bool { // To have the same name in function as external parameter name use # before parameter name
    for character in string {
        if character == characterToFind {
            return true
        }
    }
    return false
}

let containsAV = containsCharacter(string: "aardvark", characterToFind: "v") // containsAV equals true, because "aardvark" contains a "v"
```

## Function Types

```swift
func addTwoInts(a: Int, b: Int) -> Int {
    return a + b
} // Function is of type (Int, Int) -> Int

func multiplyTwoInts(a: Int, b: Int) -> Int {
    return a * b
} // Antoher function that is of type (Int, Int) -> Int

func printHelloWorld() {
    println("Hello, World!")
} // Function is of type () -> ()
```

### Using Function Types

```swift
var mathFunction: (Int, Int) -> Int = addTwoInts // Creates a variable mathFunction and sets it to refer to function addTwoInts

// Now mathFunction can be used as addTwoInts
println("Result: \(mathFunction(2, 3))") // Prints "Result: 5"

mathFunction = multiplyTwoInts // mathFunction is assigned a function multplyTwoInts

// Now mathFunction can be used as multiplyTwoInts
println("Result: \(mathFunction(2, 3))") // Prints "Result: 6"

// Type can be inferred by Swift automatically
var anotherMathFunction = addTwoInts
```

### Using Function Types as Parameter Types

```swift
func printMathResult(mathFunction: (Int, Int) -> Int, a: Int, b: Int) {
    println("Result: \(mathFunction(a, b))")
} // First parameter is a function, second and third are of type Int

printMathResult(addTwoInts, 3, 5) // Prints "Result: 8"
```

### Function Types as Return Types

```swift
func stepForward(input: Int) -> Int {
    return input + 1
}

func stepBackward(input: Int) -> Int {
    return input - 1
}

func chooseStepFunction(backwards: Bool) -> (Int) -> Int {
    return backwards ? stepBackward : stepForward
} // Returns a function of type (Int) -> Int

var currentValue = 3
let moveNearerToZero = chooseStepFunction(currentValue > 0)
// moveNearerToZero now refers to the stepBackward() function

while currentValue != 0 { // we use moveNearerToZero as reference to stepBackward()
    println("\(currentValue)")
    currentValue = moveNearerToZero(currentValue)
} // Prints "3", "2", "1"
```

### Nested Functions

```swift
func chooseStepFunctionModified(backwards: Bool) -> (Int) -> Int {
    // Declaring two new functions in a scope of a function
    func stepForward(input: Int) -> Int { return input + 1 }
    func stepBackward(input: Int) -> Int { return input - 1 }
    return backwards ? stepBackward : stepForward
} // Returns a function of type (Int) -> Int

var anotherCurrentValue = -4
let anotherMoveNearerToZero = chooseStepFunctionModified(currentValue > 0)
// anotherMoveNeareToZero now refers to the nested stepForward() function

while anotherCurrentValue != 0 {
    println("\(anotherCurrentValue)")
    anotherCurrentValue = anotherMoveNearerToZero(anotherCurrentValue)
} // Prints "-4", "-3", "-2", "-1"
```