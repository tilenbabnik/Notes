# Basic Operators

## Assignment Operator
The assignment operator initializes or updates the value of a with the value of b.

If the right side of the assignment is a tuple with multiple values, its elements can be decomposed into multiple constants or variables at once.

```swift
var b = 10
var a = 5
a = b // a is now equal to 10

var (x, y) = (10, 12) // x is equal to 10, y is equal to 12
```

## Arithmetic Operators

Basic mathematic operations. Swift supports the four standard arithmetic operators for all number types.

* addition (+)
* subtratction (-)
* multiplication (*)
* division (/)

```swift
1 + 2 // equals 3
5 - 3 // equals 2
2 * 3 // equals 6
10.0 / 2.5 // equals 4.0

"hello " + "world" // equals "hello world"
```

## Remainder Operator
The remainder operator works out how many multiples of b will fit inside a and returns the value that si left over.

```swift
10 % 3 // equals 1
8 % 2.5   // equals 0.5
```

## Increment and Decrement Operators
Increment operator (++) and a decrement operator (--) as a shortcut to increase or decrease the value of a numeric variable by 1.

Order of the operator is important. If operator is written before the value it returns already incremented value. If it's written after the value it returns original value and then increments it.

```swift
var i = 0
i = i + 1 // i now equals 1
++i // i now equals 2

--i // i now equals 1
i = i - 1 // i now equals 0

i++ // It returns a value of 0 but on the next line i will have a value of 1
i-- // It returns a value of 1 but on the next line i will have a value of 0
```

## Unary Operators
The sign of a numeric value can be toggled using a prefixed -, known as the unary minus operator. Unary plus operator doen't do anything but can be used to provide simmetry with unary minus operator.

```swift
var five = 5
var minusFive = -five // minusFive equals -5 (- is prepended without any white space)

var minusSix = -6
var six = +minusSix // six now equals 6 ( + is prepended without any white space)
```

## Compound Assignment Operators
It combines any arithmetic operator with assignment operator to perform both tasks at the same time.

```swift
var c = 3
c += 2 // Two operations combined into one (every arithmetic operator)
c = c + 2 // Does the same as line above
```

## Comparison Operators
Each of the comparison operators returns a Bool value to indicate whether or not the statement is true. Comparison operators are often used in conditional statements, such as the if statement.

* Equal to (a == b)
* Not equal to (a != b)
* Greater than (a > b)
* Less than (a < b)
* Greater than or equal to (a >= b)
* Less than or equal to (a <= b)

```swift
1 == 1 // true
2 != 1 // true
2 > 1 // true
1 < 2 // true
1 >= 1 // true
2 <= 1 // false
```

## Ternary Conditional Operator
The ternary conditional operator is a special operator with three parts, which takes the form `question ? answer1 : answer2`. It is a shortcut for evaluating one of two expressions based on whether question is true or false. If question is true, it evaluates answer1 and returns its value; otherwise, it evaluates answer2 and returns its value.

```swift
var baby = ""
var isAFemale = true

if isAFemale { // if it's a female is true name baby Sarah else name it John
    baby = "Sarah"
} else {
    baby = "John"
} // baby is now assigned "Sarah"

baby = isAFemale ? "Karen" : "Jack" // baby is now assigned "Karen"
```

## Nil Coalescing Operator
The nil coalescing operator (a ?? b) unwraps an optional a if it contains a value, or returns a default value b if a is nil. The expression a is always of an optional type. The expression b must match the type that is stored inside a.

```swift
let defaultColorName = "red"
var userDefinedColorName: String?   // defaults to nil
 
var colorNameToUse = userDefinedColorName ?? defaultColorName
// userDefinedColorName is nil, so colorNameToUse is set to the default of "red"
```

## Range Operators

### Closed Range Operator
The closed range operator (a...b) defines a range that runs from a to b, and includes the values a and b. The value of a must not be greater than b.

```swift
for index in 1...5 {
    println("\(index) times 5 is \(index * 5)")
} // Prints "1 times 5 is 5", "2 times 5 is 10"...
```

### Half-Open Range Operator
The half-open range operator (a..<b) defines a range that runs from a to b, but does not include b. It is said to be half-open because it contains its first value, but not its final value. As with the closed range operator, the value of a must not be greater than b. If the value of a is equal to b, then the resulting range will be empty.

```swift
var names = ["Anna", "Alex", "Brian", "Jack"]
for i in 0..<names.count {
    println("Person \(i + 1) is called \(names[i])")
} // Prints "Person 1 is called Anna", ...
```

## Logical Operators

### Logical NOT Operator
The logical NOT operator (!a) inverts a Boolean value so that true becomes false, and false becomes true.

```swift
var allowedEntry = false
if !allowedEntry {
    println("Access Denied")
} // Prints "Access Denied"
```

### Logical AND Operator
The logical AND operator (a && b) creates logical expressions where both values must be true for the overall expression to also be true.

```swift
var enteredDoorCode = true
var passedRetinaScan = false
if enteredDoorCode && passedRetinaScan {
    println("Welcome")
} else {
    println("Access Denied")
} // Prints "Access Denied"
```

### Logical OR Operator
The logical OR operator (a || b) is an infix operator made from two adjacent pipe characters. You use it to create logical expressions in which only one of the two values has to be true for the overall expression to be true.

```swift
var hasDoorKey = false
var knowsOverridePassword = true
if hasDoorKey || knowsOverridePassword {
    println("Welcome")
} else {
    println("Access Denied")
} // Prints "Welcome"
```