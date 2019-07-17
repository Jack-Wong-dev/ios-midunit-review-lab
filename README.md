## Mid Unit-1 Review


## Strings

1. **Given a String, return a String with each letter uppercased**

Input: `Hello, there`

Output: `HELLO, THERE`

```swift
var str = "Hello, there"
print(str.uppercased())
```

2. **Given a String, return a String alternating between uppercase and lowercase letters**


Input: `Hello, there`

Output: `HeLlO, tHeRe`

```swift
var str = "Hello, there"
var answerQ2 = String()
var strArr = Array(str)
var index = 0

for i in 0..<strArr.count{
    if i % 2 == 0{
        answerQ2.append(strArr[i].uppercased())
    }else{
        answerQ2.append(strArr[i].lowercased())
    }
}
print(answerQ2)
```


3. **Given a String, return a String with all occurrences of a given letter removed**

Input: `Hello, there`

Output: `Hllo, thr`

```swift
var str = "Hello, there"
var answerQ3 = str.replacingOccurrences(of: "e", with: "")
print(answerQ3)
```


## Arrays


1. **Given an array of type [Int], return the largest element**

Input: `[1,5,2,4,1,4]`

Output: `5`

```swift
let arr = [1,5,2,4,1,4]

let maxNumber = arr.reduce(arr[0]) { $0 > $1 ? $0 : $1 }
print(maxNumber)
```

2. **Given an array of type [Int], return the smallest element**

Input: `[1,5,2,4,1,4]`

Output: `1`

```swift
let arr = [1,5,2,4,1,4]

let minNumber = arr.reduce(arr[0]) { $0 < $1 ? $0 : $1 }
print(minNumber)
```

3. **Given an array of type [Int], return its sum**

Input: `[1,5,2,4,1,4]`

Output: `17`

```swift
let arr = [1,5,2,4,1,4]

var sum = arr.reduce(0, +)
print(sum)
```

4. **Given an array of type [Double], return its average**

Input: `[3,4.5,7.5,2,1]`

Output: `3.6`

```swift
let arr = [3,4.5,7.5,2,1]

var average = (arr.reduce(0, +))/Double(arr.count)
print(average)
```

5. **Given an array of type [Double] and a Double, return the sum of all numbers in the array greater than a given number**

Input: `[3,4.5,7.5,2,1], 3`

Output: `12`

```swift
let arr = [3,4.5,7.5,2,1]
let n: Double = 3

let sumOfNumGreater = arr.filter {$0 > n}.reduce(0, +)
print(sumsumOfNumGreater)
```


6. **Given an array of type [Double], return the product of all the elements**

Input: `[3,4.5,7.5,2,1]`

Output: `202.5`

```swift
let arr = [3,4.5,7.5,2,1]

let productOfAllElem = arr.reduce(1, *)
print(productOfAllElem)
```

7. **Given an array of type [Int], return the second smallest value in the array**

Input: `[3,6,1,9,4,8]`

Output: `3`

```swift
var arr = [3,6,1,9,4,8]
arr.sort()
var firstIndexValue = arr[0]

for i in arr where firstIndexValue < i{
    print(i)
    break
}

```

## Optionals

1. **Given an array of type [String?] return an array of [String] removing all nil values**

Input: `[nil, "We", "come", nil, "in", "peace"]`

Output: `["We", "come", "in", "peace"]`

```swift
var arr = [nil, "We", "come", nil, "in", "peace"]
var result = [String]()

for i in arr{
    if let s = i {
        result.append(s)
    }
}
print(result)
```

2. **Given an array of type [String?]? return an array of [String] removing all nil values**

Input: `nil`

Output: `[]`

```swift
var arr: [String?]? = [nil]
var result = [String]()

if let arr1 = arr{
    for i in arr1{
        if let s = i {
            result.append(s)
        }
    }
}
print(result)

```

3. **Given an array of type [Int?] return the sum of all non-nil values.  Use guard statements in your solution.**

Input: `[4, nil, 9, 5, nil]`

Output: `18`

```swift

let input = [4, nil, 9, 5, nil]
var sum = 0

for i in input{
    guard let number = i
    else{
        continue
    }
    sum += number
}
print(sum)

```

4. **Given an array of type [Int?]? return the sum of all non-nil values.  Use guard statements in your solution.**

Input: `nil`

Output: `0`

```swift
let input: [Int?]? = [nil]
var sum = 0
if let input1 = input{
    for i in input1{
        guard let number = i
        else{
            continue
        }
        sum += number
    }
}
print(sum)
```

5. **Given an array of type [Int?] and an optional Int, return the sum of all values not equal to the given number.  If the given number is nil, return the sum of all non-nil values.**

Input: `[1, 1, nil, 3, 5, nil, 1, nil, 3, 5, nil, 5, nil, 3], 1`

Output: `24`

```swift

var arr = [1, 1, nil, 3, 5, nil, 1, nil, 3, 5, nil, 5, nil, 3]
var n: Int? = 1


func sum(_ arr:[Int?],_ number: Int?)-> Int{
    var sum = 0
    if number == nil{
        for i in arr where i != nil{
            sum += i!
        }
    }else{
        for i in arr where i != nil && i! > n!{
            sum += i!
        }
    }
    return sum
}
print(sum(arr, n))

```

## Dictionaries

1. **Given an array of type [String], return a copy of the array with all duplicate values removed**

Input: `["apple", "apple", "banana", "banana", "banana", "cake", "cake"]`

Output: `["apple", "banana", "cake"]`

```swift

var arr = ["apple", "apple", "banana", "banana", "banana", "cake", "cake"]

var dict = [String:Int]()
var answer = [String]()

for i in arr{
    if dict.keys.contains(i){
        dict.updateValue(dict[i]! + 1, forKey: i)
    }else{
        dict[i] = 1
    }
}

for (key,_) in dict{
    answer.append(key)
}

print(answer)

```
```swift
//Using Set
let arr = ["apple", "apple", "banana", "banana", "banana", "cake", "cake"]

print(Set(arr))
```

2. **Given a String, find the most frequently occurring letter**

Input: `Never trust a computer you can't throw out a window ~ Steve Wozniak`

Output: `t`


```swift
let str = "Never trust a computer you can't throw out a window ~ Steve Wozniak"
var arr = Array(str.lowercased())
var dict = [Character:Int]()
let alphabet = "abcdefghijklmnopqrstuvwxyz"

for c in arr where alphabet.contains(c.lowercased()){
    if dict.keys.contains(c){
        dict.updateValue(dict[c]! + 1, forKey: c)
    }else{
        dict[c] = 1
    }
}

var mostFrequentValue = 0
var mostFrequentLetter = String()

for (key,value) in dict{
    if mostFrequentValue < value{
        mostFrequentValue = value
        mostFrequentLetter = String(key)
    }
}
print(mostFrequentLetter)
```

3. **Given an array of type [Int], return a copy of the array that contains only elements that appear at least twice**

Input: `[1,1,2,3,3,3,4,5,6,6,7]`

Output: `[1,3,6]`

```swift
let input = [1,1,2,3,3,3,4,5,6,6,7]
var dict = [Int:Int]()

for i in input{
    if dict.keys.contains(i){
        if let value = dict[i]{
            dict[i] = value + 1
        }
    }else{
        dict[i] = 1
    }
}

var output = [Int]()
for (key,value) in dict{
    if value >= 2{
        output.append(key)
    }
}
print(output.sorted())
```

4. **Given a String, find the second most frequently occurring letter in a string**

Input: `Never trust a computer you can't throw out a window ~ Steve Wozniak`

Output `o`

```swift
let input = "Never trust a computer you can't throw out a window ~ Steve Wozniak"
let alphabet = "abcdefghijklmnopqrstuvwxyz"
var frequencyDict = [Character: Int]()

for character in input where alphabet.contains(character.lowercased()){
    if let value = frequencyDict[character] {
        frequencyDict[character] = value + 1
    } else {
        frequencyDict[character] = 1
    }
}

var mostFrequent = (Character(" "), 0)
var secondMostFrequent = mostFrequent
for (key, value) in frequencyDict where value > mostFrequent.1 {
    secondMostFrequent = mostFrequent
    mostFrequent = (key, value)
}

print("The most frequent letter is \(secondMostFrequent.0) with \(secondMostFrequent.1) occurances.")
```

## Closures

1. **Given an array of type [String], return an array that contains the Strings sorted alphabetically with capital letters first (Swift will do that part automatically)**

Input: `["Never", "trust", "a", "computer", "you", "can't", "throw", "out", "a", "window"]`

Output: `["Never", "a", "a", "can\'t", "computer", "out", "throw", "trust", "window", "you"]`

```swift
let input = ["Never", "trust", "a", "computer", "you", "can't", "throw", "out", "a", "window"]

print(input.sorted(by: <))
```

2. **Given an array of type [String], return an array that contains the Strings sorted by length**

Input: `["Never", "trust", "a", "computer", "you", "can't", "throw", "out", "a", "window"]`

Output: `["a", "a", "you", "out", "Never", "trust", "can\'t", "throw", "window", "computer"]`

```swift

let input = ["Never", "trust", "a", "computer", "you", "can't", "throw", "out", "a", "window"]

print(input.sorted(by: {$0.count < $1.count}))
```

3. **Given an array of type [String], return an array containing all Strings at least 4 characters long**

Input: `["Never", "trust", "a", "computer", "you", "can't", "throw", "out", "a", "window"]`

Output: `["Never", "trust", "computer", "can\'t", "throw", "window"]`

```swift

var arr = ["Never", "trust", "a", "computer", "you", "can't", "throw", "out", "a", "window"]

print(arr.filter {$0.count >= 4})
```

4. **Given an array of type [String], return a String containing all of the Strings from the array combined and separated by spaces.  Do this first without using the `joined(separator:) method`**

Input: `["Never", "trust", "a", "computer", "you", "can't", "throw", "out", "a", "window"]`

Output: `Never trust a computer you can't throw out a window`

```swift

let input = ["Never", "trust", "a", "computer", "you", "can't", "throw", "out", "a", "window"]

print(input.reduce("", {$0 + " " + $1}))
```

## Enums


1. **Given an array of type [Int] and an instance of NumberType (defined below), return an array containing only all the even or odd numbers.**

```swift
enum NumberType {
    case even
    case odd
}
```
Input: `[1,2,3,4,5,6], NumberType.odd`

Output: `[1,3,5]`

```swift
enum NumberType {
    case even
    case odd

    func evenOrOdd(arr:[Int]) -> [Int]{
        var result = [Int]()
        switch self{
            case .even:
                result = arr.filter {$0 % 2 == 0}
            case .odd:
                result = arr.filter {$0 % 2 != 0}
        }   
        return result
    }
}

let number = [1,2,3,4,5,6]
var answer = NumberType.odd
print(answer.evenOrOdd(arr: number))
```


2. **Given a String and an instance of StringType (defined below), return the String either lowercased or uppercased**

```swift
enum StringType {
    case lowercase
    case uppercase
}
```

Input: `"Design is not just what it looks like and feels like. Design is how it works", .uppercase`

Output: ``"DESIGN IS NOT JUST WHAT IT LOOKS LIKE AND FEELS LIKE. DESIGN IS HOW IT WORKS"``

```swift

enum StringType {
    case lowercase(String)
    case uppercase(String)

    func changeCase() -> String{
        switch self {
            case .lowercase(let input):
                return input.lowercased()
            case .uppercase(let input):
                return input.uppercased()
        }
    }
}

let str = "Design is not just what it looks like and feels like. Design is how it works"
var answer = StringType.lowercase(str)
print(answer.changeCase())
```

3. **Given an array of type [FileStatus] (defined below) and an Int, return an array containing only files that were saved more than that many times**

```swift
enum FileStatus: CustomStringConvertible {
    case unsaved
    case saved(numberOfVersions: Int)
    var description: String {
        switch self {
        case .unsaved: return "Unsaved File"
        case let .saved(numberOfVersions): return "File that has been saved \(numberOfVersions) times"
        }
    }
}
```

Input: `[FileStatus.saved(numberOfVersions: 5), FileStatus.saved(numberOfVersions: 3), FileStatus.saved(numberOfVersions: 8)], 4`

Output: `[File that has been saved 5 times, File that has been saved 8 times]`

```swift
enum FileStatus: CustomStringConvertible {
    case unsaved
    case saved(numberOfVersions: Int)
    
    var description: String {
        switch self {
            case .unsaved: return "Unsaved File"
            case let .saved(numberOfVersions): return "File that has been saved \(numberOfVersions) times"
        }
    }

    func getVersions() -> Int?{
        switch self {
            case .unsaved:
                return nil
            case .saved(let numberOfVersions):
                return numberOfVersions
        }
    }
}

let input = [FileStatus.saved(numberOfVersions: 5), FileStatus.saved(numberOfVersions: 3), FileStatus.saved(numberOfVersions: 8)]

let n = 4

print(input.filter {$0.getVersions()! > n})

```
