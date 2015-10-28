# Collection Types

## Arrays
An array stores values of the same type in an ordered list. The same value can appear in an array multiple times at different positions.

```swift
var shoppingList: [String] = ["Eggs", "Milk"] // shoppingList was initialized with two items
var watchList = ["Harry Potter", "Iron Man"] // another array (type isn't neccesary)
```

### Creating and Initializing an Array
You can create an empty array of a cerain type using initializer syntax.

```swift
var someInts = [Int]() // Array initializer of type [Int]

someInts.append(3) // someInts now contain 1 value of type Int
someInts = [] // someInts is now an empty array but it's still of type [Int]
```

Swift’s Array type also provides an initializer for creating an array of a certain size with all of its values set to a provided default value.

```swift
var threeDoubles = [Double](count: 3, repeatedValue: 0.0) // initializes an array of type [Double] with three items with value 0.0
var anotherThreeDoubles = [Double](count: 3, repeatedValue: 2.5) // another array now with three items with values 2.5
```

You can create a new array by adding together two existing arrays with compatible types with the addition operator (+). The new array’s type is inferred from the type of the two arrays you add together.

```swift
var sixDoubles = threeDoubles + anotherThreeDoubles // array of type [Double] that equals [0.0, 0.0, 0.0, 2.5, 2.5, 2.5]
```

### Accessing and Modifying an Array
To find out the number of items in an array, check its read-only count property.

```swift
println("The shopping list contains \(shoppingList.count) items.") // Prints "The shopping list contains 2 items."
```

Use the Boolean isEmpty property as a shortcut for checking whether the count property is equal to 0.

```swift
if shoppingList.isEmpty {
    println("The shopping list is empty")
} else {
    println("The shopping list is not empty")
} // Prints "The shopping list is not empty"
```

You can add a new item to the end of an array by calling the array’s append(_:) method.

```swift
shoppingList.append("Flour")
```

Alternatively, append an array of one or more compatible items with the addition assignment operator (+=).

```swift
shoppingList += ["Baking Powder"] // shoppingList now contains 4 items
shoppingList += ["Chocolate Spread", "Cheese", "Butter"] // shoppingList now contains 7 items
```

Retrieve a value from the array by using subscript syntax, passing the index of the value you want to retrieve within square brackets immediately after the name of the array.

```swift
var firstItem = shoppingList[0] // firstItem is equal to "Eggs"
```

You can use subscript syntax to change an existing value at a given index.

```swift
shoppingList[3] = "3 Baking Powders" // Fourth item is now "3 Baking Powders" rather than before "Baking Powder"
```

You can also use subscript syntax to change a range of values at once, even if the replacement set of values has a different length than the range you are replacing.

```swift
shoppingList[4...6] = ["Bananas", "Apples"] // shoppingList now contains 6 items
```

To insert an item into the array at a specified index, call the array’s insert(_:atIndex:) method.

```swift
shoppingList.insert("Maple Syrup", atIndex: 2) // shoppingList now contains 7 items, "Maple Syrup" was added in position 3
```

Similarly, you remove an item from the array with the removeAtIndex(_:) method. This method removes the item at the specified index and returns the removed item.

```swift
var deletedValue = shoppingList.removeAtIndex(2) // shoppingList now contains 6 items, deletedValue is assigned a value of "Maple Syrup"
```

If you want to remove the final item from an array, use the removeLast() method.

```swift
var lastItem = shoppingList.removeLast()
```

To remove all items from an array use removeAll() method.

```swift
shoppingList.removeAll()
```

### Iterating Over an Array
You can iterate over the entire set of values in an array with the for-in loop.

```swift
for item in shoppingList {
    println(item)
} // "Eggs", "Milk", "Flour", "3 Baking Powders", "Bananas"
```

To get the index of a value use enumerate function like this.

```swift
for (index, value) in enumerate(shoppingList) {
    println("item \(index + 1): \(value)")
} // "Item 1: Eggs", "Item 2: Milk", "Item 3: Flour", "Item 4: 3 Baking Powder", "Item 5: Bananas"
```

## Sets

```swift
var favoriteGenres: Set<String> = ["Rock", "Classical", "Hip Hop"] // favoriteGenres has been initialized with three initial items
var favoriteMovies: Set = ["Harry Potter", "Romeo and Juliet"] // Collection type Set must be written exclusively, <String> can be left out
```

### Creating and Initialzing a Set

```swift
var letters = Set<Character>() // Set initializer of type Character

letters.insert("a") // letters now contain 1 value of type Character
letters = [] // letter is now an empty set but it's still of type Character
```

### Accessing and modifying a Set

```swift
// To count the number of items in a set use count property
println("I have \(favoriteGenres.count) favorite music genres") // Prints "I have 3 favorite music genres"

// To check if a set has stored values use isEmpty property
if favoriteGenres.isEmpty {
    println("As far as music goes I'm not picky")
} else {
    println("I have particular music preferences")
} // Prints "I have particular music preferences"

// To add a new item to the set use insert() method
favoriteGenres.insert("Jazz")

// Items can be removed from set with remove() or removeAll() methods
if let removedGenre = favoriteGenres.remove("Rock") {
    println("\(removedGenre)? I'm over that.")
} else {
    println("I never much cared for that")
} // Prints "Rock? I'm over that."

// To check if a set contains a particular item use the contains() method
if favoriteGenres.contains("Funk") {
    println("I get up on the good foot")
} else {
    println("It's too funky in here")
} // Prints "It's too funky in here"
```

### Iterating over a Set

```swift
for genre in favoriteGenres {
    println(genre)
} // "Classical", "Hip Hop", "Jazz"
```

### Set operations

```swift
var oddDigits: Set = [1, 3, 5, 7, 9]
var evenDigits: Set = [0, 2, 4, 6, 8]
let singleDigitPrimeNumbers: Set = [2, 3, 5, 7]

// Use union() method to create new set with all values from both sets
sorted(oddDigits.union(evenDigits)) // [0, 1, 2, 3, 4, 5, 6, 7, 8, 9]

// Use subtract() method to create new set with values not in the specified set
sorted(oddDigits.subtract(singleDigitPrimeNumbers)) // [1, 9]

// Use intersect() method to create new set with values common in both sets
sorted(oddDigits.intersect(evenDigits)) // []

// Use exclusiveOr() method to create new set with values in either set but not both
sorted(oddDigits.exclusiveOr(singleDigitPrimeNumbers)) // [1, 2, 9]
```

### Comparing Sets

```swift
var houseAnimals: Set = ["Dog", "Cat"]
var farmAnimals: Set = ["Cow", "Chicken", "Sheep", "Dog", "Cat"]
var cityAnimals: Set = ["Pigeon", "Mouse"]

// Use is equal == operator to determine it two sets contain all of the same elements
houseAnimals == farmAnimals // false

// Use the isSubsetOf() method to determine if all of the values of a set are contained in specified set
houseAnimals.isSubsetOf(farmAnimals) // true

// Use the isSupersetOf() method to determine whether a set contains all of the values in specified set
farmAnimals.isSupersetOf(houseAnimals) // true

// Use the isDisjointWith() method to determine whether two sets have any values in common
farmAnimals.isDisjointWith(cityAnimals) // true
```

## Dictionaries

```swift
var airports: [String: String] = ["YYZ": "Toronto Pearson", "DUB": "Dublin"] // airports has been initialized with two initial items
var actorsInMovies = ["Harry Potter": "Daniel Radcliffe", "Iron Man": "Johnny Depp"] // another dictionary (type isn't neccesary)
```

### Creating an empty Dictionary

```swift
var namesOfIntegers = [Int: String]() // namesOfIntegers is an empty [Int: String] dictionary

namesOfIntegers[16] = "sixteen" // namesOfIntegers now contains 1 key-value pair
namesOfIntegers = [:] // namesOfIntegers is once again an empty dictionary of type [Int: String]
```

### Accessing and modifying a Dictionary

```swift
println("The airports dictionary contains \(airports.count) items.") // Prints "The airports dictionary contains 2 items."

// To check if dictionary has stored values use isEmpty property
if airports.isEmpty {
    println("The airport dictionary is empty")
} else {
    println("The airport dictionary is not empty")
} // Prints "The airport dictionary is not empty"

// New items can also be added with = operator
airports["LHR"] = "London" // The airports dictionary now contains 3 items

// Also use subscript syntax to change the value associated with a particular key
airports["LHR"] = "London Heathrow" // The value for "LHR" has been changed to "London Heathrow"

// Another way to change a value for a key is to use updateValue() method, this method also returns old value
airports.updateValue("Dublin Airport", forKey: "DUB") // "Dublin"

// To remove a key-value also use subscript syntax and nil for values
airports["APL"] = "Apple International" // not a real airport so we will delete it in next step
airports["APL"] = nil // "APL" was removed from the dictionary

// Anothey way to remove key-value pair is to use removeValueForKey() method, this method also returns removed value
airports.removeValueForKey("DUB") // "Dublin Airport"
```

### Iteratin over a Dictionary

```swift
for (airportCode, airportName) in airports {
    println("\(airportCode): \(airportName)")
} // "YYZ: Toronto Pearson", "LHR: London Heathrow"

// Accessing only keys or values
for airportCode in airports.keys {
    println("Airport code: \(airportCode)")
} // "Airport code: YYZ", "Airport code: LHR"

// To convert keys or values to an array initialize a new array with keys or values property
var airportNames = [String](airports.values)
```