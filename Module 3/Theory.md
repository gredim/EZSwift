# Управляющие структуры

## 1. Условные операторы (`if`, `else`, `switch`)

### Использование `if` и `else`

Условные операторы позволяют программе принимать решения и выполнять разные действия в зависимости от условия.

В языке Swift основным условным оператором является `if`. Он проверяет выражение на истинность и выполняет блок кода, если условие истинно. Если условие ложно, можно использовать оператор `else` для выполнения другого блока кода.

**Синтаксис:**
```swift
if условие {
    // Код, если условие истинно
} else {
    // Код, если условие ложно
}
```

**Пример**:
```swift
let temperature = 25

if temperature > 30 {
    print("Очень жарко!")
} else {
    print("Температура комфортная.")
}
// Вывод: Температура комфортная.
```

Можно также использовать несколько условий, комбинируя их с `else if`:

```swift
if temperature > 30 {
    print("Очень жарко!")
} else if temperature > 20 {
    print("Температура комфортная.")
} else {
    print("Холодно!")
}
// Вывод: Температура комфортная.
```

### Оператор `switch` и его особенности

`switch` — это более мощный и гибкий инструмент для работы с условиями, чем if. Он позволяет проверять одно значение по нескольким вариантам и выполнять разные блоки кода в зависимости от совпадения.

**Особенности `switch`**:

- В отличие от других языков, в Swift не нужно использовать `break` после каждого случая, так как выполнение автоматически завершится.
- `switch` может работать не только с простыми значениями, но и с диапазонами, кортежами и даже условиями.

**Синтаксис:**
```swift
switch выражение {
case значение1:
    // Действие для значения1
case значение2:
    // Действие для значения2
default:
    // Действие, если ни одно из значений не совпало
}
```

**Пример**:
```swift
let day = 3

switch day {
case 1:
    print("Понедельник")
case 2:
    print("Вторник")
case 3:
    print("Среда")
case 4:
    print("Четверг")
case 5:
    print("Пятница")
default:
    print("Выходной")
}
// Вывод: Среда
```

Можно использовать диапазоны:
```swift
let age = 25

switch age {
case 0..<13:
    print("Детство")
case 13..<18:
    print("Подросток")
case 18..<60:
    print("Взрослый")
default:
    print("Пенсионер")
}
// Вывод: Взрослый
```

---

## 2. Циклы (`for`, `while`)

Циклы позволяют многократно выполнять один и тот же код, пока выполняется некоторое условие.

### Цикл `for-in`
Цикл `for-in` используется для перебора элементов коллекции (массивов, словарей, диапазонов и т.д.).

**Синтаксис:**
```swift
for элемент in коллекция {
    // Действия с элементом
}
```

**Пример**:
```swift
let numbers = [1, 2, 3, 4, 5]

for number in numbers {
    print(number)
}
// Вывод: 1 2 3 4 5
```

Также можно использовать `for-in` с диапазонами чисел:
```swift
for i in 1...5 { // Диапазон от 1 до 5 (включительно)
    print(i)
}
// Вывод: 1 2 3 4 5
```

### Цикл `while`

Цикл `while` выполняет блок кода, пока условие остаётся истинным. Условие проверяется перед каждой итерацией.

**Синтаксис:**
```swift
while условие {
    // Действия, пока условие истинно
}
```

**Пример**:
```swift
var counter = 1

while counter <= 5 {
    print(counter)
    counter += 1
}
// Вывод: 1 2 3 4 5
```

### Цикл `repeat-while`

Цикл `repeat-while` похож на `while`, но в отличие от него, условие проверяется после выполнения блока кода, то есть блок выполняется хотя бы один раз.

**Синтаксис:**
```swift
repeat {
    // Действия
} while условие
```

**Пример**:
```swift
var counter = 1

repeat {
    print(counter)
    counter += 1
} while counter <= 5
// Вывод: 1 2 3 4 5
```

---

## 3. Преждевременный выход из цикла

В Swift для досрочного выхода из цикла можно использовать операторы `break` и `continue`.

### Оператор `break`

Оператор `break` используется для немедленного завершения работы цикла, независимо от того, выполняется ли условие.

**Пример**:
```swift
for i in 1...10 {
    if i == 5 {
        break
    }
    print(i)
}
// Вывод: 1 2 3 4
```

В этом примере цикл завершится, как только значение `i` станет равным 5.

### Оператор `continue`

Оператор `continue` пропускает оставшуюся часть текущей итерации цикла и переходит к следующей. Это полезно, когда нужно пропустить некоторые шаги, но продолжить выполнение цикла.

**Пример**:
```swift
for i in 1...5 {
    if i == 3 {
        continue
    }
    print(i)
}
// Вывод: 1 2 4 5
```

Здесь, когда значение `i` равно 3, итерация пропускается и цикл продолжается с 4.

---

## Полезные материалы и ссылки:

1. **[Официальная документация Swift](https://developer.apple.com/documentation/swift)**:
Официальное руководство по языку Swift — это первый и самый важный ресурс для изучения всех аспектов языка, включая управляющие структуры.

2. **[Hacking with Swift](https://www.hackingwithswift.com/)**:
Авторитетный источник по Swift с упором на практическое изучение языка через создание приложений. Особое внимание уделено синтаксису и работе с циклами и условиями.