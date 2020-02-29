# Swift和Kotlin基础语法比较

***内容翻译自Github项目：[Swift is like Kotlin](https://github.com/dengdasam/swift-is-like-kotlin)***

## Hello World

#### Swift

```Swift
print("Hello, world!")
```

#### Kotlin

```Kotlin
println("Hello, world!")
```
## 变量和常量

#### Swift
```Swift
var myVariable = 42
myVariable = 50
let myConstant = 42
```

#### Kotlin

```Kotlin
var myVariable = 42
myVariable = 50
val myConstant = 42
```

## 显式类型

#### Swift

```Swift
let explicitDouble: Double = 70
```

#### Kotlin


```Kotlin
val explicitDouble: Double = 70.0
```

## 类型转换

#### Swift

Swift需显式转换

```Swift
let label = "The width is "
let width = 94
let widthLabel = label + String(width)
```

#### Kotlin

Kotlin可以隐式转换

```Kotlin
val label = "The width is "
val width = 94
val widthLabel = label + width
```

## 字符串插值

#### Swift

Swift使用 “\” 符号

```Swift
let apples = 3
let oranges = 5
let fruitSummary = "I have \(apples + oranges) " +
"pieces of fruit."
```

#### Kotlin

Kotlin使用 “$” 符号

```Kotlin
val apples = 3
val oranges = 5
val fruitSummary = "I have ${apples + oranges} " +
"pieces of fruit."
```


## 区间运算

#### Swift
```Swift
et names = ["Anna", "Alex", "Brian", "Jack"]
et count = names.count
for i in 0..<count {
print("Person \(i + 1) is called \(names[i])")
// Person 1 is called Anna
// Person 2 is called Alex
// Person 3 is called Brian
// Person 4 is called Jack
```

```Swift
for index in 1...5 {
print("\(index) times 5 is \(index * 5)")
}
// 1 times 5 is 5
// 2 times 5 is 10
// 3 times 5 is 15
// 4 times 5 is 20
// 5 times 5 is 25
```

#### Kotlin

```Kotlin
val names = arrayOf("Anna", "Alex", "Brian", "Jack")
val count = names.count()
for (i in 0..count - 1) {
println("Person ${i + 1} is called ${names[i]}")
}
// Person 1 is called Anna
// Person 2 is called Alex
// Person 3 is called Brian
// Person 4 is called Jack
```

```Kotlin
for (index in 1..5) {
println("$index times 5 is ${index * 5}")
}
// 1 times 5 is 5
// 2 times 5 is 10
// 3 times 5 is 15
// 4 times 5 is 20
// 5 times 5 is 25
```

## 数组

#### Swift
```Swift
var shoppingList = ["catfish", "water",
"tulips", "blue paint"]
shoppingList[1] = "bottle of water"
```

#### Kotlin

```Kotlin
val shoppingList = arrayOf("catfish", "water",
"tulips", "blue paint")
shoppingList[1] = "bottle of water"
```

## 字典

Swift使用 ":" 连接 key value

#### Swift
```Swift
var occupations = [
"Malcolm": "Captain",
"Kaylee": "Mechanic",
]
occupations["Jayne"] = "Public Relations"
```

#### Kotlin

Kotlin使用“to” 关键字 连接key value

```Kotlin
val occupations = mutableMapOf(
"Malcolm" to "Captain",
"Kaylee" to "Mechanic"
)
occupations["Jayne"] = "Public Relations"
```

## 空集

#### Swift
```Swift
let emptyArray = [String]()
let emptyDictionary = [String: Float]()
```

#### Kotlin

```Kotlin
val emptyArray = arrayOf<String>()
val emptyMap = mapOf<String, Float>()
```

## 函数定义

#### Swift
```Swift
func greet(_ name: String,_ day: String) -> String {
return "Hello \(name), today is \(day)."
}
greet("Bob", "Tuesday")
```

#### Kotlin

```Kotlin
fun greet(name: String, day: String): String {
return "Hello $name, today is $day."
}
greet("Bob", "Tuesday")
```

## 可变数量参数

#### Swift
```Swift
func sumOf(_ numbers: Int...) -> Int {
var sum = 0
for number in numbers {
sum += number
}
return sum
}
sumOf(42, 597, 12)
```

#### Kotlin

```Kotlin
fun sumOf(vararg numbers: Int): Int {
var sum = 0
for (number in numbers) {
sum += number
}
return sum
}
sumOf(42, 597, 12)
// 也可以使用另一种更简短的定义方法
fun sumOf(vararg numbers: Int) = numbers.sum()
```

## 函数类型

#### Swift
```Swift
func makeIncrementer() -> (Int -> Int) {
func addOne(number: Int) -> Int {
return 1 + number
}
return addOne
}
let increment = makeIncrementer()
increment(7)
```

#### Kotlin

```Kotlin
fun makeIncrementer(): (Int) -> Int {
val addOne = fun(number: Int): Int {
return 1 + number
}
return addOne
}
val increment = makeIncrementer()
increment(7)
// 也可以使用另一种更简短的写法
fun makeIncrementer() = fun(number: Int) = 1 + number
```
## Map映射

#### Swift

Swift使用 $ 

```Swift
let numbers = [20, 19, 7, 12]
numbers.map { 3 * $0 }
```

#### Kotlin

Kotlin使用 it 

```Kotlin
val numbers = listOf(20, 19, 7, 12)
numbers.map { 3 * it }
```

## Sort排序

#### Swift
```Swift
var mutableArray = [1, 5, 3, 12, 2]
mutableArray.sort()
```

#### Kotlin

```Kotlin
listOf(1, 5, 3, 12, 2).sorted()
```

## 具名参数

#### Swift
```Swift
func area(width: Int, height: Int) -> Int {
    return width * height
}
area(width: 2, height: 3)
```

#### Kotlin

Kotlin混用位置参数与具名参数时，所有位置参数都要放在第一个具名参数之前。例如，允许调用 f(1, y = 2) 但不允许 f(x = 1, 2)。

```Kotlin
fun area(width: Int, height: Int) = width * height
area(width = 2, height = 3)

// This is also possible with named arguments
area(2, height = 2)
area(height = 3, width = 2)
```

## 类定义

#### Swift
```Swift
class Shape {
    var numberOfSides = 0
    func simpleDescription() -> String {
        return "A shape with \(numberOfSides) sides."
    }
}
```

#### Kotlin

```Kotlin
class Shape {
    var numberOfSides = 0
    fun simpleDescription() =
        "A shape with $numberOfSides sides."
}
```

## 对象实例化

#### Swift
```Swift
var shape = Shape()
shape.numberOfSides = 7
var shapeDescription = shape.simpleDescription()
```

#### Kotlin

```Kotlin
var shape = Shape()
shape.numberOfSides = 7
var shapeDescription = shape.simpleDescription()
```

## 子类继承

#### Swift
```Swift
class NamedShape {
    var numberOfSides: Int = 0
    let name: String

    init(name: String) {
        self.name = name
    }

    func simpleDescription() -> String {
        return "A shape with \(numberOfSides) sides."
    }
}

class Square: NamedShape {
    var sideLength: Double

    init(sideLength: Double, name: String) {
        self.sideLength = sideLength
        super.init(name: name)
        self.numberOfSides = 4
    }

    func area() -> Double {
        return sideLength * sideLength
    }

    override func simpleDescription() -> String {
        return "A square with sides of length " +
	       sideLength + "."
    }
}

let test = Square(sideLength: 5.2, name: "square")
test.area()
test.simpleDescription()
```

#### Kotlin

Kotlin类继承，需在父类用open关键字显式声明

```Kotlin
open class NamedShape(val name: String) {
    var numberOfSides = 0

    open fun simpleDescription() =
        "A shape with $numberOfSides sides."
}

class Square(var sideLength: BigDecimal, name: String) :
        NamedShape(name) {
    init {
        numberOfSides = 4
    }

    fun area() = sideLength.pow(2)

    override fun simpleDescription() =
        "A square with sides of length $sideLength."
}

val test = Square(BigDecimal("5.2"), "square")
test.area()
test.simpleDescription()
```

## 对象类型检查

#### Swift
```Swift
var movieCount = 0
var songCount = 0

for item in library {
    if item is Movie {
        movieCount += 1
    } else if item is Song {
        songCount += 1
    }
}
```

#### Kotlin

```Kotlin
var movieCount = 0
var songCount = 0

for (item in library) {
    if (item is Movie) {
        ++movieCount
    } else if (item is Song) {
        ++songCount
    }
}
```

## 变量匹配

#### Swift

Swift使用switch函数，同时去掉了break

```Swift
let nb = 42
switch nb {
    case 0...7, 8, 9: print("single digit")
    case 10: print("double digits")
    case 11...99: print("double digits")
    case 100...999: print("triple digits")
    default: print("four or more digits")
}
```

#### Kotlin

Kotlin引入了新的when语句，来处理变量匹配，同时在when内使用“->”箭头函数

```Kotlin
val nb = 42
when (nb) {
    in 0..7, 8, 9 -> println("single digit")
    10 -> println("double digits")
    in 11..99 -> println("double digits")
    in 100..999 -> println("triple digits")
    else -> println("four or more digits")
}
```

## 遍历对象

#### Swift

Swift for语句去掉了（）

```Swift
for current in someObjects {
    if let movie = current as? Movie {
        print("Movie: '\(movie.name)', " +
            "dir. \(movie.director)")
    }
}
```

#### Kotlin

Kotlin for语句保留了（）

```Kotlin
for (current in someObjects) {
    if (current is Movie) {
        println("Movie: '${current.name}', " +
	    "dir. ${current.director}")
    }
}
```

## 接口

#### Swift

Swift使用 protocol 关键字

```Swift
protocol Nameable {
    func name() -> String
}

func f<T: Nameable>(x: T) {
    print("Name is " + x.name())
}
```

#### Kotlin

Kotlin使用 interface 关键字

```Kotlin
interface Nameable {
    fun name(): String
}

fun f<T: Nameable>(x: T) {
    println("Name is " + x.name())
}
```

## 扩展



#### Swift
Swift需使用extension关键字

```Swift
extension Double {
    var km: Double { return self * 1_000.0 }
    var m: Double { return self }
    var cm: Double { return self / 100.0 }
    var mm: Double { return self / 1_000.0 }
    var ft: Double { return self / 3.28084 }
}
let oneInch = 25.4.mm
print("One inch is \(oneInch) meters")
// 输出 "One inch is 0.0254 meters"
let threeFeet = 3.ft
print("Three feet is \(threeFeet) meters")
// 输出 "Three feet is 0.914399970739201 meters"
```

#### Kotlin
Kotlin则直接使用“.”符号

```Kotlin
val Double.km: Double get() = this * 1000
val Double.m: Double get() = this
val Double.cm: Double get() = this / 100
val Double.mm: Double get() = this / 1000
val Double.ft: Double get() = this / 3.28084

val oneInch = 25.4.mm
println("One inch is $oneInch meters")
// 输出 "One inch is 0.0254 meters"
val threeFeet = 3.0.ft
println("Three feet is $threeFeet meters")
// 输出 "Three feet is 0.914399970739201 meters"
```

---

亲爱的朋友；相对Swift和Kotlin的语法，你们更喜欢哪一种呢？当然Swift和Kotlin都是非常现代化的编程语言，在很多方面都已经趋同类似，两个都是非常优秀的语言。

---
以下是英文原文介绍
---

# Swift is like Kotlin

Page: http://nilhcem.github.io/swift-is-like-kotlin/

Programmatically inspired from [swift-is-like-go](https://github.com/jiyinyiyong/swift-is-like-go) and visually inspired from [swiftislikescala](https://github.com/leverich/swiftislikescala)

### License

MIT

### Develop

```bash
npm i # install dependencies to build tools
./make.coffee dev # build html
```

HTML is generated from `cirru/index.cirru`.
Read that file and you would know what's happening.
