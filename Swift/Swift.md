# Swift Basics and Examples

This document contains basic concepts and examples of Swift programming, including variable declarations, control flow, arrays, dictionaries, and handling optional values.

---

## Table of Contents
1.   [Simple Values](https://docs.swift.org/swift-book/documentation/the-swift-programming-language/guidedtour/#Simple-Values)
2.   [Control Flow](https://docs.swift.org/swift-book/documentation/the-swift-programming-language/guidedtour/#Control-Flow)

---

## 1. Variable Declarations
Swift variables can be declared with type inference or explicit type annotations.

```swift
let implicitInteger = 70
let implicitDouble = 70.0
let explicitDouble: Double = 70
let explicitFloat: Float = 4
```

## 2. Type Conversion
Swift enforces strict type safety, so types must be explicitly converted when needed.

```swift
let label = "The width is "
let width = 94
let widthLabel = label + String(width) // Correct
// let widthLabel = label + width // Error: Cannot add String and Int
```
Using string interpolation for simpler type conversion:

```swift
let apples = 3
let oranges = 5
let fruitSummary = "I have \(apples + oranges) fruits."
print(fruitSummary) // Output: I have 8 fruits.
```
Multi-line strings with interpolation:

```swift
let quotation = """
Even though there's whitespace to the left,
the actual lines aren't indented.
I have \(apples + oranges) pieces of fruit.
"""
print(quotation)
```

## 3. Arrays and Dictionaries
Swift provides flexible and type-safe arrays and dictionaries.
Arrays
```swift
var fruits = ["strawberries", "limes", "tangerines"]
fruits[1] = "grapes"
fruits.append("blueberries")
print(fruits) // Output: ["strawberries", "grapes", "tangerines", "blueberries"]
fruits = [] // Reset array
```
Dictionaries
```swift
var occupations = [
    "Malcolm": "Captain",
    "Kaylee": "Mechanic"
]
occupations["Jayne"] = "Public Relations"
print(occupations)
occupations = [:] // Reset dictionary
```

## 4. Control Flow
### For Loops
```swift
let individualScores = [75, 62, 89, 100, 34]
var teamScore = 0

for score in individualScores {
    if score > 50 {
        teamScore += 3
    } else {
        teamScore += 1
    }
}
print(teamScore) // Output: 13
```

### While and Repeat-While Loops
```swift
var n = 2
while n < 100 {
    n *= 2
}
print(n) // Output: 128

var m = 2
repeat {
    m *= 2
} while m < 100
print(m) // Output: 128
```

---

## 5. Optionals
Optionals represent the absence of a value.

```swift
var optionalName: String? = nil
var greeting = "Hello!"
if let name = optionalName {
    greeting = "Hello, \(name)"
}
print(greeting) // Output: Hello!
```

Using the `??` operator for default values:
```swift
let nickname: String? = nil
let fullName: String = "John Appleseed"
let informalGreeting = "Hi \(nickname ?? fullName)"
print(informalGreeting) // Output: Hi John Appleseed
```

---

## 6. Switch Statements
Switches in Swift must be exhaustive and can include patterns.

```swift
let vegetable = "red pepper"
switch vegetable {
case "celery":
    print("Add some raisins and make ants on a log.")
case "cucumber", "watercress":
    print("That would make a good tea sandwich.")
case let x where x.hasSuffix("pepper"):
    print("Is it a spicy \(x)?")
default:
    print("Everything tastes good in soup.")
}
// Output: Is it a spicy red pepper?
```

---

## 7. Loops and Dictionaries
### Nested Loops
```swift
let interestingNumbers = [
    "Prime": [2, 3, 5, 7, 11, 13],
    "Fibonacci": [1, 1, 2, 3, 5, 8],
    "Square": [1, 4, 9, 16, 25]
]
var largest = 0
var largestKind = ""

for (kind, numbers) in interestingNumbers {
    for number in numbers {
        if number > largest {
            largest = number
            largestKind = kind
        }
    }
}
print(largest) // Output: 25
print(largestKind) // Output: Square
```
### Find the Largest Prime Number
```swift
if let primeNumbers = interestingNumbers["Prime"] {
    let largestPrime = primeNumbers.max() ?? 0
    print("Largest Prime number is \(largestPrime)")
}
// Output: Largest Prime number is 13
```

---

## 8. Input and Output
### Sum of Input Numbers
```swift
// Read input and calculate sum
if let input = readLine() {
    let numbers = input.split(separator: " ").compactMap { Int($0) }
    let sum = numbers.reduce(0, +)
    print(sum)
}
```

Alternate version:
```swift
let a = readLine()!.split(separator: " ").map { Int($0)! }
print(a[0] + a[1])
```

---

## Problem
1.    [acmic:1000](https://www.acmicpc.net/problem/1000)

## Summary
This document covered:
1. Declaring variables and type conversions.
2. Arrays and dictionaries.
3. Control flow structures including loops and conditionals.
4. Handling optional values effectively.
5. Using Swift's powerful `switch` statements.

This serves as a beginner-friendly reference for fundamental Swift programming concepts.

Reference : [AppleDevloper](https://docs.swift.org/swift-book/documentation/the-swift-programming-language/guidedtour)
