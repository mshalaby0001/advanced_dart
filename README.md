# advanced_dart

## Core libraries

Here’s a summary of the **[Dart Libraries documentation](https://dart.dev/libraries)**, using the same method you provided, with explanations and **code examples** where applicable:

---

### **Dart Libraries**
Dart provides a rich set of core libraries that cover a wide range of functionalities, from basic data structures to asynchronous programming and file I/O. These libraries are essential for building robust Dart applications.

---

### **1. Core Libraries**
The Dart core libraries include essential utilities for everyday programming tasks.

#### **dart:core**
- **Description**: Provides basic types (e.g., `int`, `String`, `List`) and utilities (e.g., `DateTime`, `RegExp`).
- **Example**:
  ```dart
  void main() {
    String message = 'Hello, Dart!';
    print(message.toUpperCase()); // Output: HELLO, DART!
  }
  ```

#### **dart:math**
- **Description**: Provides mathematical constants and functions.
- **Example**:
  ```dart
  import 'dart:math';

  void main() {
    print(pi); // Output: 3.141592653589793
    print(sqrt(16)); // Output: 4.0
  }
  ```

#### **dart:convert**
- **Description**: Provides encoders and decoders for JSON, UTF-8, and other formats.
- **Example**:
  ```dart
  import 'dart:convert';

  void main() {
    Map<String, dynamic> user = {'name': 'John', 'age': 30};
    String jsonString = jsonEncode(user);
    print(jsonString); // Output: {"name":"John","age":30}
  }
  ```

---

### **2. Asynchronous Programming**
Dart provides libraries for working with asynchronous code, such as futures and streams.

#### **dart:async**
- **Description**: Provides `Future` and `Stream` classes for asynchronous programming.
- **Example**:
  ```dart
  import 'dart:async';

  Future<void> fetchData() async {
    await Future.delayed(Duration(seconds: 2));
    print('Data fetched!');
  }

  void main() {
    fetchData();
    print('Fetching data...');
  }
  ```

#### **dart:isolate**
- **Description**: Provides support for concurrent programming using isolates.
- **Example**:
  ```dart
  import 'dart:isolate';

  void isolateFunction(SendPort sendPort) {
    sendPort.send('Hello from isolate!');
  }

  void main() async {
    ReceivePort receivePort = ReceivePort();
    Isolate.spawn(isolateFunction, receivePort.sendPort);

    receivePort.listen((message) {
      print(message); // Output: Hello from isolate!
    });
  }
  ```

---

### **3. File and Network I/O**
Dart provides libraries for working with files and network requests.

#### **dart:io**
- **Description**: Provides APIs for file I/O, sockets, HTTP, and more.
- **Example**:
  ```dart
  import 'dart:io';

  void main() async {
    File file = File('example.txt');
    await file.writeAsString('Hello, Dart!');
    String content = await file.readAsString();
    print(content); // Output: Hello, Dart!
  }
  ```

#### **dart:html**
- **Description**: Provides APIs for browser-based applications (web-only).
- **Example**:
  ```dart
  import 'dart:html';

  void main() {
    querySelector('#output')?.text = 'Hello, Dart!';
  }
  ```

---

### **4. Collections and Utilities**
Dart provides libraries for working with collections and other utilities.

#### **dart:collection**
- **Description**: Provides additional collection types (e.g., `Queue`, `LinkedHashMap`).
- **Example**:
  ```dart
  import 'dart:collection';

  void main() {
    Queue<int> queue = Queue();
    queue.add(1);
    queue.add(2);
    print(queue.removeFirst()); // Output: 1
  }
  ```

#### **dart:typed_data**
- **Description**: Provides lists for handling typed data (e.g., `Uint8List`, `Float32List`).
- **Example**:
  ```dart
  import 'dart:typed_data';

  void main() {
    Uint8List bytes = Uint8List(4);
    bytes[0] = 0xDE;
    bytes[1] = 0xAD;
    bytes[2] = 0xBE;
    bytes[3] = 0xEF;
    print(bytes); // Output: [222, 173, 190, 239]
  }
  ```

---

### **5. Example: Full Workflow**
Here’s an example of a complete workflow using Dart libraries:

#### **Step 1: Use dart:core**
```dart
void main() {
  String message = 'Hello, Dart!';
  print(message.toUpperCase()); // Output: HELLO, DART!
}
```

#### **Step 2: Use dart:async**
```dart
import 'dart:async';

Future<void> fetchData() async {
  await Future.delayed(Duration(seconds: 2));
  print('Data fetched!');
}

void main() {
  fetchData();
  print('Fetching data...');
}
```

#### **Step 3: Use dart:io**
```dart
import 'dart:io';

void main() async {
  File file = File('example.txt');
  await file.writeAsString('Hello, Dart!');
  String content = await file.readAsString();
  print(content); // Output: Hello, Dart!
}
```

#### **Step 4: Use dart:convert**
```dart
import 'dart:convert';

void main() {
  Map<String, dynamic> user = {'name': 'John', 'age': 30};
  String jsonString = jsonEncode(user);
  print(jsonString); // Output: {"name":"John","age":30}
}
```

---

### **Summary of Dart Libraries**
| Library               | Description                              | Example                                   |
|-----------------------|------------------------------------------|-------------------------------------------|
| **dart:core**         | Basic types and utilities                | `String.toUpperCase()`                    |
| **dart:math**         | Mathematical constants and functions     | `sqrt(16)`                                |
| **dart:convert**      | JSON and UTF-8 encoding/decoding         | `jsonEncode({'name': 'John'})`            |
| **dart:async**        | Asynchronous programming                 | `Future.delayed(Duration(seconds: 2))`    |
| **dart:isolate**      | Concurrent programming                   | `Isolate.spawn(isolateFunction, sendPort)`|
| **dart:io**           | File and network I/O                     | `File('example.txt').readAsString()`      |
| **dart:html**         | Browser-based APIs (web-only)            | `querySelector('#output')?.text = 'Hello'`|
| **dart:collection**   | Additional collection types              | `Queue<int>()`                            |
| **dart:typed_data**   | Typed data lists                         | `Uint8List(4)`                            |

---

### **Example: Full Dart Libraries Workflow**
Here’s an example of a complete workflow using Dart libraries:

#### **Step 1: Use dart:core**
```dart
void main() {
  String message = 'Hello, Dart!';
  print(message.toUpperCase()); // Output: HELLO, DART!
}
```

#### **Step 2: Use dart:async**
```dart
import 'dart:async';

Future<void> fetchData() async {
  await Future.delayed(Duration(seconds: 2));
  print('Data fetched!');
}

void main() {
  fetchData();
  print('Fetching data...');
}
```

#### **Step 3: Use dart:io**
```dart
import 'dart:io';

void main() async {
  File file = File('example.txt');
  await file.writeAsString('Hello, Dart!');
  String content = await file.readAsString();
  print(content); // Output: Hello, Dart!
}
```

#### **Step 4: Use dart:convert**
```dart
import 'dart:convert';

void main() {
  Map<String, dynamic> user = {'name': 'John', 'age': 30};
  String jsonString = jsonEncode(user);
  print(jsonString); // Output: {"name":"John","age":30}
}
```

---

## List Class

Here’s a summary of the **[List class documentation](https://api.flutter.dev/flutter/dart-core/List-class.html)** from the Dart core library, using the same method you provided, with explanations and **code examples** where applicable:

---

### **List Class in Dart**
The `List` class in Dart represents an ordered collection of objects. It is one of the most commonly used data structures and provides a wide range of methods for manipulating and accessing elements.

---

### **1. Creating a List**
- **Description**: Lists can be created using literals or constructors.
- **Use Case**: Store and manage collections of data.

#### Example:
```dart
void main() {
  // Using a list literal
  List<int> numbers = [1, 2, 3, 4, 5];

  // Using the List constructor
  List<String> fruits = List.filled(3, 'Apple');

  print(numbers); // Output: [1, 2, 3, 4, 5]
  print(fruits);  // Output: [Apple, Apple, Apple]
}
```

---

### **2. Accessing Elements**
- **Description**: Access elements using the index operator `[]`.
- **Use Case**: Retrieve specific elements from the list.

#### Example:
```dart
void main() {
  List<String> colors = ['Red', 'Green', 'Blue'];
  print(colors[0]); // Output: Red
  print(colors[2]); // Output: Blue
}
```

---

### **3. Adding Elements**
- **Description**: Add elements to the list using methods like `add`, `addAll`, or `insert`.
- **Use Case**: Dynamically grow the list.

#### Example:
```dart
void main() {
  List<String> colors = ['Red', 'Green'];

  // Add a single element
  colors.add('Blue');

  // Add multiple elements
  colors.addAll(['Yellow', 'Purple']);

  // Insert an element at a specific index
  colors.insert(1, 'Orange');

  print(colors); // Output: [Red, Orange, Green, Blue, Yellow, Purple]
}
```

---

### **4. Removing Elements**
- **Description**: Remove elements using methods like `remove`, `removeAt`, or `removeLast`.
- **Use Case**: Dynamically shrink the list.

#### Example:
```dart
void main() {
  List<String> colors = ['Red', 'Green', 'Blue', 'Yellow'];

  // Remove a specific element
  colors.remove('Green');

  // Remove an element at a specific index
  colors.removeAt(1);

  // Remove the last element
  colors.removeLast();

  print(colors); // Output: [Red]
}
```

---

### **5. Iterating Over a List**
- **Description**: Use loops or methods like `forEach` to iterate over the list.
- **Use Case**: Process each element in the list.

#### Example:
```dart
void main() {
  List<int> numbers = [1, 2, 3, 4, 5];

  // Using a for loop
  for (int number in numbers) {
    print(number);
  }

  // Using forEach
  numbers.forEach((number) {
    print(number);
  });
}
```

---

### **6. Sorting a List**
- **Description**: Sort the list using the `sort` method.
- **Use Case**: Arrange elements in a specific order.

#### Example:
```dart
void main() {
  List<int> numbers = [5, 3, 1, 4, 2];
  numbers.sort();
  print(numbers); // Output: [1, 2, 3, 4, 5]
}
```

---

### **7. Filtering a List**
- **Description**: Use the `where` method to filter elements.
- **Use Case**: Create a new list with elements that match a condition.

#### Example:
```dart
void main() {
  List<int> numbers = [1, 2, 3, 4, 5];
  List<int> evenNumbers = numbers.where((number) => number % 2 == 0).toList();
  print(evenNumbers); // Output: [2, 4]
}
```

---

### **8. Mapping a List**
- **Description**: Use the `map` method to transform elements.
- **Use Case**: Create a new list with transformed elements.

#### Example:
```dart
void main() {
  List<int> numbers = [1, 2, 3, 4, 5];
  List<String> stringNumbers = numbers.map((number) => 'Number $number').toList();
  print(stringNumbers); // Output: [Number 1, Number 2, Number 3, Number 4, Number 5]
}
```

---

### **9. Example: Full Workflow**
Here’s an example of a complete workflow using the `List` class:

#### **Step 1: Create a List**
```dart
void main() {
  List<int> numbers = [1, 2, 3, 4, 5];
  print(numbers); // Output: [1, 2, 3, 4, 5]
}
```

#### **Step 2: Add Elements**
```dart
void main() {
  List<int> numbers = [1, 2, 3];
  numbers.add(4);
  numbers.addAll([5, 6]);
  print(numbers); // Output: [1, 2, 3, 4, 5, 6]
}
```

#### **Step 3: Remove Elements**
```dart
void main() {
  List<int> numbers = [1, 2, 3, 4, 5];
  numbers.remove(3);
  numbers.removeAt(0);
  print(numbers); // Output: [2, 4, 5]
}
```

#### **Step 4: Iterate Over the List**
```dart
void main() {
  List<int> numbers = [1, 2, 3, 4, 5];
  numbers.forEach((number) {
    print(number);
  });
}
```

#### **Step 5: Sort the List**
```dart
void main() {
  List<int> numbers = [5, 3, 1, 4, 2];
  numbers.sort();
  print(numbers); // Output: [1, 2, 3, 4, 5]
}
```

#### **Step 6: Filter the List**
```dart
void main() {
  List<int> numbers = [1, 2, 3, 4, 5];
  List<int> evenNumbers = numbers.where((number) => number % 2 == 0).toList();
  print(evenNumbers); // Output: [2, 4]
}
```

#### **Step 7: Map the List**
```dart
void main() {
  List<int> numbers = [1, 2, 3, 4, 5];
  List<String> stringNumbers = numbers.map((number) => 'Number $number').toList();
  print(stringNumbers); // Output: [Number 1, Number 2, Number 3, Number 4, Number 5]
}
```

---

### **Summary of List Features**
| Feature               | Description                              | Example                                   |
|-----------------------|------------------------------------------|-------------------------------------------|
| **Create List**       | Initialize a list                        | `List<int> numbers = [1, 2, 3];`         |
| **Access Elements**   | Retrieve elements by index               | `numbers[0]`                              |
| **Add Elements**      | Add elements to the list                 | `numbers.add(4)`                          |
| **Remove Elements**   | Remove elements from the list            | `numbers.remove(3)`                       |
| **Iterate**           | Loop through the list                    | `numbers.forEach((number) => print(number))`|
| **Sort**              | Sort the list                            | `numbers.sort()`                          |
| **Filter**            | Filter elements based on a condition     | `numbers.where((number) => number % 2 == 0)`|
| **Map**               | Transform elements                       | `numbers.map((number) => 'Number $number')`|

---

### **Example: Full List Workflow**
Here’s an example of a complete workflow using the `List` class:

#### **Step 1: Create a List**
```dart
void main() {
  List<int> numbers = [1, 2, 3, 4, 5];
  print(numbers); // Output: [1, 2, 3, 4, 5]
}
```

#### **Step 2: Add Elements**
```dart
void main() {
  List<int> numbers = [1, 2, 3];
  numbers.add(4);
  numbers.addAll([5, 6]);
  print(numbers); // Output: [1, 2, 3, 4, 5, 6]
}
```

#### **Step 3: Remove Elements**
```dart
void main() {
  List<int> numbers = [1, 2, 3, 4, 5];
  numbers.remove(3);
  numbers.removeAt(0);
  print(numbers); // Output: [2, 4, 5]
}
```

#### **Step 4: Iterate Over the List**
```dart
void main() {
  List<int> numbers = [1, 2, 3, 4, 5];
  numbers.forEach((number) {
    print(number);
  });
}
```

#### **Step 5: Sort the List**
```dart
void main() {
  List<int> numbers = [5, 3, 1, 4, 2];
  numbers.sort();
  print(numbers); // Output: [1, 2, 3, 4, 5]
}
```

#### **Step 6: Filter the List**
```dart
void main() {
  List<int> numbers = [1, 2, 3, 4, 5];
  List<int> evenNumbers = numbers.where((number) => number % 2 == 0).toList();
  print(evenNumbers); // Output: [2, 4]
}
```

#### **Step 7: Map the List**
```dart
void main() {
  List<int> numbers = [1, 2, 3, 4, 5];
  List<String> stringNumbers = numbers.map((number) => 'Number $number').toList();
  print(stringNumbers); // Output: [Number 1, Number 2, Number 3, Number 4, Number 5]
}
```

---

## Generic Collection

Here’s a summary of the **[Generics in Dart](https://dart.dev/language/generics#generic-collections-and-the-types-they-contain)** documentation, focusing on **generic collections and the types they contain**, using the same method you provided, with explanations and **code examples** where applicable:

---

### **Generics in Dart**
Generics allow you to write type-safe code by parameterizing types. They are especially useful for collections like `List`, `Set`, and `Map`, enabling you to specify the type of elements they contain.

---

### **1. Generic Collections**
- **Description**: Generic collections allow you to define the type of elements they can hold, ensuring type safety at compile time.
- **Use Case**: Create collections that work with specific types.

#### Example: Generic List
```dart
void main() {
  // List of integers
  List<int> numbers = [1, 2, 3, 4, 5];

  // List of strings
  List<String> fruits = ['Apple', 'Banana', 'Cherry'];

  print(numbers); // Output: [1, 2, 3, 4, 5]
  print(fruits);  // Output: [Apple, Banana, Cherry]
}
```

#### Example: Generic Set
```dart
void main() {
  // Set of integers
  Set<int> uniqueNumbers = {1, 2, 3, 4, 5};

  // Set of strings
  Set<String> uniqueFruits = {'Apple', 'Banana', 'Cherry'};

  print(uniqueNumbers); // Output: {1, 2, 3, 4, 5}
  print(uniqueFruits);  // Output: {Apple, Banana, Cherry}
}
```

#### Example: Generic Map
```dart
void main() {
  // Map with String keys and int values
  Map<String, int> fruitPrices = {
    'Apple': 1,
    'Banana': 2,
    'Cherry': 3,
  };

  print(fruitPrices); // Output: {Apple: 1, Banana: 2, Cherry: 3}
}
```

---

### **2. Type Safety**
- **Description**: Generics ensure type safety by restricting the types of elements that can be added to a collection.
- **Use Case**: Prevent runtime errors by catching type mismatches at compile time.

#### Example: Type Safety in Lists
```dart
void main() {
  List<int> numbers = [1, 2, 3];

  // This will cause a compile-time error
  // numbers.add('Four'); // Error: The argument type 'String' can't be assigned to the parameter type 'int'.

  numbers.add(4); // Valid
  print(numbers); // Output: [1, 2, 3, 4]
}
```

---

### **3. Generic Methods**
- **Description**: Methods can also be generic, allowing them to work with any type.
- **Use Case**: Write reusable methods that operate on different types.

#### Example: Generic Method
```dart
T getFirst<T>(List<T> list) {
  return list.first;
}

void main() {
  List<int> numbers = [1, 2, 3];
  List<String> fruits = ['Apple', 'Banana', 'Cherry'];

  print(getFirst(numbers)); // Output: 1
  print(getFirst(fruits));  // Output: Apple
}
```

---

### **4. Generic Classes**
- **Description**: Classes can be generic, allowing them to work with any type.
- **Use Case**: Create reusable classes that operate on different types.

#### Example: Generic Class
```dart
class Box<T> {
  T value;

  Box(this.value);

  T getValue() {
    return value;
  }
}

void main() {
  Box<int> intBox = Box(42);
  Box<String> stringBox = Box('Hello');

  print(intBox.getValue());    // Output: 42
  print(stringBox.getValue()); // Output: Hello
}
```

---

### **5. Example: Full Workflow**
Here’s an example of a complete workflow using generics:

#### **Step 1: Generic List**
```dart
void main() {
  List<int> numbers = [1, 2, 3, 4, 5];
  print(numbers); // Output: [1, 2, 3, 4, 5]
}
```

#### **Step 2: Generic Set**
```dart
void main() {
  Set<String> uniqueFruits = {'Apple', 'Banana', 'Cherry'};
  print(uniqueFruits); // Output: {Apple, Banana, Cherry}
}
```

#### **Step 3: Generic Map**
```dart
void main() {
  Map<String, int> fruitPrices = {
    'Apple': 1,
    'Banana': 2,
    'Cherry': 3,
  };
  print(fruitPrices); // Output: {Apple: 1, Banana: 2, Cherry: 3}
}
```

#### **Step 4: Generic Method**
```dart
T getFirst<T>(List<T> list) {
  return list.first;
}

void main() {
  List<int> numbers = [1, 2, 3];
  print(getFirst(numbers)); // Output: 1
}
```

#### **Step 5: Generic Class**
```dart
class Box<T> {
  T value;

  Box(this.value);

  T getValue() {
    return value;
  }
}

void main() {
  Box<int> intBox = Box(42);
  print(intBox.getValue()); // Output: 42
}
```

---

### **Summary of Generics Features**
| Feature               | Description                              | Example                                   |
|-----------------------|------------------------------------------|-------------------------------------------|
| **Generic List**      | List with a specific type                | `List<int> numbers = [1, 2, 3];`         |
| **Generic Set**       | Set with a specific type                 | `Set<String> fruits = {'Apple', 'Banana'};`|
| **Generic Map**       | Map with specific key and value types    | `Map<String, int> fruitPrices = {'Apple': 1};`|
| **Type Safety**       | Ensures collections contain only the specified type | `List<int> numbers = [1, 2, 3]; numbers.add('Four'); // Error` |
| **Generic Methods**   | Methods that work with any type          | `T getFirst<T>(List<T> list) { ... }`     |
| **Generic Classes**   | Classes that work with any type          | `class Box<T> { ... }`                    |

---

### **Example: Full Generics Workflow**
Here’s an example of a complete workflow using generics:

#### **Step 1: Generic List**
```dart
void main() {
  List<int> numbers = [1, 2, 3, 4, 5];
  print(numbers); // Output: [1, 2, 3, 4, 5]
}
```

#### **Step 2: Generic Set**
```dart
void main() {
  Set<String> uniqueFruits = {'Apple', 'Banana', 'Cherry'};
  print(uniqueFruits); // Output: {Apple, Banana, Cherry}
}
```

#### **Step 3: Generic Map**
```dart
void main() {
  Map<String, int> fruitPrices = {
    'Apple': 1,
    'Banana': 2,
    'Cherry': 3,
  };
  print(fruitPrices); // Output: {Apple: 1, Banana: 2, Cherry: 3}
}
```

#### **Step 4: Generic Method**
```dart
T getFirst<T>(List<T> list) {
  return list.first;
}

void main() {
  List<int> numbers = [1, 2, 3];
  print(getFirst(numbers)); // Output: 1
}
```

#### **Step 5: Generic Class**
```dart
class Box<T> {
  T value;

  Box(this.value);

  T getValue() {
    return value;
  }
}

void main() {
  Box<int> intBox = Box(42);
  print(intBox.getValue()); // Output: 42
}
```

---

## Lambda Functions

Here’s a summary of the **[Lambda Functions in Dart](https://medium.com/jay-tillu/lambda-functions-in-dart-7db8b759f07a)** article, using the same method you provided, with explanations and **code examples** where applicable:

---

### **Lambda Functions in Dart**
Lambda functions (also known as anonymous functions or closures) are concise ways to define functions without a name. They are useful for short, one-off functions, especially when passing functions as arguments to other functions.

---

### **1. What is a Lambda Function?**
- **Description**: A lambda function is a function without a name. It is defined using the `(parameters) => expression` syntax.
- **Use Case**: Simplify code by defining small, inline functions.

#### Example:
```dart
void main() {
  // Lambda function to add two numbers
  var add = (int a, int b) => a + b;

  print(add(2, 3)); // Output: 5
}
```

---

### **2. Using Lambda Functions as Arguments**
- **Description**: Lambda functions are often used as arguments to higher-order functions like `forEach`, `map`, and `where`.
- **Use Case**: Pass behavior directly into functions.

#### Example: Using `forEach`
```dart
void main() {
  List<int> numbers = [1, 2, 3, 4, 5];

  // Lambda function as an argument to forEach
  numbers.forEach((number) => print(number));
}
```

#### Example: Using `map`
```dart
void main() {
  List<int> numbers = [1, 2, 3, 4, 5];

  // Lambda function as an argument to map
  List<int> doubledNumbers = numbers.map((number) => number * 2).toList();

  print(doubledNumbers); // Output: [2, 4, 6, 8, 10]
}
```

#### Example: Using `where`
```dart
void main() {
  List<int> numbers = [1, 2, 3, 4, 5];

  // Lambda function as an argument to where
  List<int> evenNumbers = numbers.where((number) => number % 2 == 0).toList();

  print(evenNumbers); // Output: [2, 4]
}
```

---

### **3. Lambda Functions with Multiple Statements**
- **Description**: If a lambda function requires multiple statements, use curly braces `{}` and the `return` keyword.
- **Use Case**: Define more complex behavior inline.

#### Example:
```dart
void main() {
  var processNumber = (int number) {
    if (number % 2 == 0) {
      return 'Even';
    } else {
      return 'Odd';
    }
  };

  print(processNumber(4)); // Output: Even
  print(processNumber(3)); // Output: Odd
}
```

---

### **4. Assigning Lambda Functions to Variables**
- **Description**: Lambda functions can be assigned to variables, making them reusable.
- **Use Case**: Store behavior for later use.

#### Example:
```dart
void main() {
  // Assigning a lambda function to a variable
  var greet = (String name) => 'Hello, $name!';

  print(greet('Alice')); // Output: Hello, Alice!
  print(greet('Bob'));   // Output: Hello, Bob!
}
```

---

### **5. Example: Full Workflow**
Here’s an example of a complete workflow using lambda functions:

#### **Step 1: Define a Lambda Function**
```dart
void main() {
  var add = (int a, int b) => a + b;
  print(add(2, 3)); // Output: 5
}
```

#### **Step 2: Use Lambda Function with `forEach`**
```dart
void main() {
  List<int> numbers = [1, 2, 3, 4, 5];
  numbers.forEach((number) => print(number));
}
```

#### **Step 3: Use Lambda Function with `map`**
```dart
void main() {
  List<int> numbers = [1, 2, 3, 4, 5];
  List<int> doubledNumbers = numbers.map((number) => number * 2).toList();
  print(doubledNumbers); // Output: [2, 4, 6, 8, 10]
}
```

#### **Step 4: Use Lambda Function with `where`**
```dart
void main() {
  List<int> numbers = [1, 2, 3, 4, 5];
  List<int> evenNumbers = numbers.where((number) => number % 2 == 0).toList();
  print(evenNumbers); // Output: [2, 4]
}
```

#### **Step 5: Use Lambda Function with Multiple Statements**
```dart
void main() {
  var processNumber = (int number) {
    if (number % 2 == 0) {
      return 'Even';
    } else {
      return 'Odd';
    }
  };

  print(processNumber(4)); // Output: Even
  print(processNumber(3)); // Output: Odd
}
```

#### **Step 6: Assign Lambda Function to a Variable**
```dart
void main() {
  var greet = (String name) => 'Hello, $name!';
  print(greet('Alice')); // Output: Hello, Alice!
  print(greet('Bob'));   // Output: Hello, Bob!
}
```

---

### **Summary of Lambda Functions**
| Feature               | Description                              | Example                                   |
|-----------------------|------------------------------------------|-------------------------------------------|
| **Basic Lambda**      | Concise function definition              | `(int a, int b) => a + b`                 |
| **Higher-Order Functions** | Use lambdas with `forEach`, `map`, `where` | `numbers.forEach((number) => print(number))`|
| **Multi-Statement Lambda** | Use `{}` and `return` for complex logic | `(int number) { if (number % 2 == 0) return 'Even'; else return 'Odd'; }` |
| **Assign to Variable** | Store lambdas for reuse                 | `var greet = (String name) => 'Hello, $name!';` |

---

### **Example: Full Lambda Functions Workflow**
Here’s an example of a complete workflow using lambda functions:

#### **Step 1: Define a Lambda Function**
```dart
void main() {
  var add = (int a, int b) => a + b;
  print(add(2, 3)); // Output: 5
}
```

#### **Step 2: Use Lambda Function with `forEach`**
```dart
void main() {
  List<int> numbers = [1, 2, 3, 4, 5];
  numbers.forEach((number) => print(number));
}
```

#### **Step 3: Use Lambda Function with `map`**
```dart
void main() {
  List<int> numbers = [1, 2, 3, 4, 5];
  List<int> doubledNumbers = numbers.map((number) => number * 2).toList();
  print(doubledNumbers); // Output: [2, 4, 6, 8, 10]
}
```

#### **Step 4: Use Lambda Function with `where`**
```dart
void main() {
  List<int> numbers = [1, 2, 3, 4, 5];
  List<int> evenNumbers = numbers.where((number) => number % 2 == 0).toList();
  print(evenNumbers); // Output: [2, 4]
}
```

#### **Step 5: Use Lambda Function with Multiple Statements**
```dart
void main() {
  var processNumber = (int number) {
    if (number % 2 == 0) {
      return 'Even';
    } else {
      return 'Odd';
    }
  };

  print(processNumber(4)); // Output: Even
  print(processNumber(3)); // Output: Odd
}
```

#### **Step 6: Assign Lambda Function to a Variable**
```dart
void main() {
  var greet = (String name) => 'Hello, $name!';
  print(greet('Alice')); // Output: Hello, Alice!
  print(greet('Bob'));   // Output: Hello, Bob!
}
```

---

## Functional Programming 

Here’s a summary of the **[Functional Programming with Flutter](https://buildflutter.com/functional-programming-with-flutter/)** article, using the same method you provided, with explanations and **code examples** where applicable:

---

### **Functional Programming with Flutter**
Functional programming (FP) is a programming paradigm that treats computation as the evaluation of mathematical functions and avoids changing state and mutable data. Flutter, built with Dart, supports functional programming concepts, making it easier to write clean, maintainable, and testable code.

---

### **1. Key Concepts of Functional Programming**
- **Immutability**: Data is immutable, meaning it cannot be changed after it is created.
- **Pure Functions**: Functions that always produce the same output for the same input and have no side effects.
- **Higher-Order Functions**: Functions that take other functions as arguments or return them as results.
- **Recursion**: Solving problems by breaking them down into smaller instances of the same problem.

---

### **2. Immutability**
- **Description**: Use immutable data structures to avoid side effects and make the code more predictable.
- **Use Case**: Create lists, maps, and other data structures that cannot be modified after creation.

#### Example:
```dart
void main() {
  // Immutable list
  final List<int> numbers = [1, 2, 3];

  // This will cause a compile-time error
  // numbers.add(4); // Error: Cannot add to an unmodifiable list

  // Create a new list with additional elements
  final List<int> newNumbers = [...numbers, 4];
  print(newNumbers); // Output: [1, 2, 3, 4]
}
```

---

### **3. Pure Functions**
- **Description**: Pure functions do not depend on or modify external state. They always return the same output for the same input.
- **Use Case**: Write predictable and testable functions.

#### Example:
```dart
int add(int a, int b) {
  return a + b;
}

void main() {
  print(add(2, 3)); // Output: 5
}
```

---

### **4. Higher-Order Functions**
- **Description**: Functions that take other functions as arguments or return them as results.
- **Use Case**: Pass behavior into functions, making them more flexible and reusable.

#### Example: Using `map`
```dart
void main() {
  List<int> numbers = [1, 2, 3, 4, 5];

  // Higher-order function: map
  List<int> doubledNumbers = numbers.map((number) => number * 2).toList();

  print(doubledNumbers); // Output: [2, 4, 6, 8, 10]
}
```

#### Example: Using `where`
```dart
void main() {
  List<int> numbers = [1, 2, 3, 4, 5];

  // Higher-order function: where
  List<int> evenNumbers = numbers.where((number) => number % 2 == 0).toList();

  print(evenNumbers); // Output: [2, 4]
}
```

---

### **5. Recursion**
- **Description**: Solve problems by breaking them down into smaller instances of the same problem.
- **Use Case**: Implement algorithms like factorial, Fibonacci, etc.

#### Example: Factorial Using Recursion
```dart
int factorial(int n) {
  if (n == 0 || n == 1) {
    return 1;
  }
  return n * factorial(n - 1);
}

void main() {
  print(factorial(5)); // Output: 120
}
```

---

### **6. Example: Full Workflow**
Here’s an example of a complete workflow using functional programming concepts:

#### **Step 1: Immutable Data**
```dart
void main() {
  final List<int> numbers = [1, 2, 3];
  final List<int> newNumbers = [...numbers, 4];
  print(newNumbers); // Output: [1, 2, 3, 4]
}
```

#### **Step 2: Pure Function**
```dart
int add(int a, int b) {
  return a + b;
}

void main() {
  print(add(2, 3)); // Output: 5
}
```

#### **Step 3: Higher-Order Function**
```dart
void main() {
  List<int> numbers = [1, 2, 3, 4, 5];
  List<int> doubledNumbers = numbers.map((number) => number * 2).toList();
  print(doubledNumbers); // Output: [2, 4, 6, 8, 10]
}
```

#### **Step 4: Recursion**
```dart
int factorial(int n) {
  if (n == 0 || n == 1) {
    return 1;
  }
  return n * factorial(n - 1);
}

void main() {
  print(factorial(5)); // Output: 120
}
```

---

### **Summary of Functional Programming Features**
| Feature               | Description                              | Example                                   |
|-----------------------|------------------------------------------|-------------------------------------------|
| **Immutability**      | Use immutable data structures            | `final List<int> numbers = [1, 2, 3];`   |
| **Pure Functions**    | Functions with no side effects           | `int add(int a, int b) { return a + b; }`|
| **Higher-Order Functions** | Functions that take or return functions | `numbers.map((number) => number * 2)`    |
| **Recursion**         | Solve problems by breaking them down     | `int factorial(int n) { ... }`           |

---

### **Example: Full Functional Programming Workflow**
Here’s an example of a complete workflow using functional programming concepts:

#### **Step 1: Immutable Data**
```dart
void main() {
  final List<int> numbers = [1, 2, 3];
  final List<int> newNumbers = [...numbers, 4];
  print(newNumbers); // Output: [1, 2, 3, 4]
}
```

#### **Step 2: Pure Function**
```dart
int add(int a, int b) {
  return a + b;
}

void main() {
  print(add(2, 3)); // Output: 5
}
```

#### **Step 3: Higher-Order Function**
```dart
void main() {
  List<int> numbers = [1, 2, 3, 4, 5];
  List<int> doubledNumbers = numbers.map((number) => number * 2).toList();
  print(doubledNumbers); // Output: [2, 4, 6, 8, 10]
}
```

#### **Step 4: Recursion**
```dart
int factorial(int n) {
  if (n == 0 || n == 1) {
    return 1;
  }
  return n * factorial(n - 1);
}

void main() {
  print(factorial(5)); // Output: 120
}
```

---

## Isolates

Here’s a summary of the **[How Isolates Work in Dart](https://dart.dev/language/concurrency#how-isolates-work)** documentation, using the same method you provided, with explanations and **code examples** where applicable:

---

### **How Isolates Work in Dart**
Isolates are Dart's model for concurrent programming. They allow you to run code in parallel without sharing memory, which helps avoid common concurrency issues like race conditions. Each isolate has its own memory and runs in its own thread.

---

### **1. What is an Isolate?**
- **Description**: An isolate is an independent worker that runs Dart code in parallel with other isolates. It has its own memory and event loop.
- **Use Case**: Perform computationally intensive tasks without blocking the main thread.

---

### **2. Creating and Using Isolates**
- **Description**: Use the `Isolate.spawn` method to create a new isolate. Communication between isolates is done using `SendPort` and `ReceivePort`.
- **Use Case**: Offload heavy computations to a separate isolate.

#### Example: Basic Isolate
```dart
import 'dart:isolate';

void isolateFunction(SendPort sendPort) {
  sendPort.send('Hello from isolate!');
}

void main() async {
  // Create a ReceivePort to receive messages from the isolate
  ReceivePort receivePort = ReceivePort();

  // Spawn a new isolate
  Isolate.spawn(isolateFunction, receivePort.sendPort);

  // Listen for messages from the isolate
  receivePort.listen((message) {
    print(message); // Output: Hello from isolate!
  });
}
```

---

### **3. Passing Data Between Isolates**
- **Description**: Use `SendPort` to send data to an isolate and `ReceivePort` to receive data from it.
- **Use Case**: Share data between the main isolate and worker isolates.

#### Example: Passing Data
```dart
import 'dart:isolate';

void isolateFunction(SendPort sendPort) {
  // Receive a message from the main isolate
  ReceivePort receivePort = ReceivePort();
  sendPort.send(receivePort.sendPort);

  receivePort.listen((message) {
    print('Isolate received: $message');
    sendPort.send('Echo: $message');
  });
}

void main() async {
  ReceivePort receivePort = ReceivePort();

  Isolate.spawn(isolateFunction, receivePort.sendPort);

  // Get the SendPort of the isolate
  SendPort isolateSendPort = await receivePort.first;

  // Send a message to the isolate
  isolateSendPort.send('Hello from main isolate!');

  // Listen for a response from the isolate
  receivePort.listen((message) {
    print('Main isolate received: $message'); // Output: Main isolate received: Echo: Hello from main isolate!
  });
}
```

---

### **4. Example: Full Workflow**
Here’s an example of a complete workflow using isolates:

#### **Step 1: Create an Isolate**
```dart
import 'dart:isolate';

void isolateFunction(SendPort sendPort) {
  sendPort.send('Hello from isolate!');
}

void main() async {
  ReceivePort receivePort = ReceivePort();
  Isolate.spawn(isolateFunction, receivePort.sendPort);

  receivePort.listen((message) {
    print(message); // Output: Hello from isolate!
  });
}
```

#### **Step 2: Pass Data Between Isolates**
```dart
import 'dart:isolate';

void isolateFunction(SendPort sendPort) {
  ReceivePort receivePort = ReceivePort();
  sendPort.send(receivePort.sendPort);

  receivePort.listen((message) {
    print('Isolate received: $message');
    sendPort.send('Echo: $message');
  });
}

void main() async {
  ReceivePort receivePort = ReceivePort();

  Isolate.spawn(isolateFunction, receivePort.sendPort);

  SendPort isolateSendPort = await receivePort.first;

  isolateSendPort.send('Hello from main isolate!');

  receivePort.listen((message) {
    print('Main isolate received: $message'); // Output: Main isolate received: Echo: Hello from main isolate!
  });
}
```

---

### **Summary of Isolates Features**
| Feature               | Description                              | Example                                   |
|-----------------------|------------------------------------------|-------------------------------------------|
| **Isolate Creation**  | Create a new isolate                     | `Isolate.spawn(isolateFunction, sendPort)`|
| **SendPort**          | Send data to an isolate                  | `sendPort.send('Hello')`                  |
| **ReceivePort**       | Receive data from an isolate             | `receivePort.listen((message) { ... })`   |
| **Data Passing**      | Share data between isolates              | `SendPort` and `ReceivePort`              |

---

### **Example: Full Isolates Workflow**
Here’s an example of a complete workflow using isolates:

#### **Step 1: Create an Isolate**
```dart
import 'dart:isolate';

void isolateFunction(SendPort sendPort) {
  sendPort.send('Hello from isolate!');
}

void main() async {
  ReceivePort receivePort = ReceivePort();
  Isolate.spawn(isolateFunction, receivePort.sendPort);

  receivePort.listen((message) {
    print(message); // Output: Hello from isolate!
  });
}
```

#### **Step 2: Pass Data Between Isolates**
```dart
import 'dart:isolate';

void isolateFunction(SendPort sendPort) {
  ReceivePort receivePort = ReceivePort();
  sendPort.send(receivePort.sendPort);

  receivePort.listen((message) {
    print('Isolate received: $message');
    sendPort.send('Echo: $message');
  });
}

void main() async {
  ReceivePort receivePort = ReceivePort();

  Isolate.spawn(isolateFunction, receivePort.sendPort);

  SendPort isolateSendPort = await receivePort.first;

  isolateSendPort.send('Hello from main isolate!');

  receivePort.listen((message) {
    print('Main isolate received: $message'); // Output: Main isolate received: Echo: Hello from main isolate!
  });
}
```

---

## Async / Await 

Here’s a summary of the **[Async/Await in Dart](https://dart.dev/libraries/async/async-await)** documentation, using the same method you provided, with explanations and **code examples** where applicable:

---

### **Async/Await in Dart**
`async` and `await` are keywords in Dart that make asynchronous programming easier and more readable. They allow you to write asynchronous code that looks similar to synchronous code.

---

### **1. What is Async/Await?**
- **Description**: 
  - `async`: Marks a function as asynchronous, allowing it to use `await`.
  - `await`: Pauses the execution of an `async` function until a `Future` completes.
- **Use Case**: Simplify asynchronous code by avoiding nested callbacks.

---

### **2. Basic Usage**
- **Description**: Use `async` to define an asynchronous function and `await` to wait for the result of a `Future`.
- **Use Case**: Perform asynchronous operations like network requests or file I/O.

#### Example:
```dart
Future<void> fetchData() async {
  print('Fetching data...');
  await Future.delayed(Duration(seconds: 2)); // Simulate a network request
  print('Data fetched!');
}

void main() {
  fetchData();
  print('Fetching data in progress...');
}
```

**Output**:
```
Fetching data...
Fetching data in progress...
Data fetched!
```

---

### **3. Returning Values from Async Functions**
- **Description**: An `async` function returns a `Future`. Use `return` to provide a value when the `Future` completes.
- **Use Case**: Return results from asynchronous operations.

#### Example:
```dart
Future<String> fetchUserName() async {
  await Future.delayed(Duration(seconds: 2)); // Simulate a network request
  return 'John Doe';
}

void main() async {
  String userName = await fetchUserName();
  print('User: $userName'); // Output: User: John Doe
}
```

---

### **4. Error Handling**
- **Description**: Use `try-catch` blocks to handle errors in asynchronous code.
- **Use Case**: Handle exceptions that occur during asynchronous operations.

#### Example:
```dart
Future<void> fetchData() async {
  try {
    print('Fetching data...');
    await Future.delayed(Duration(seconds: 2)); // Simulate a network request
    throw Exception('Failed to fetch data'); // Simulate an error
  } catch (e) {
    print('Error: $e'); // Output: Error: Exception: Failed to fetch data
  }
}

void main() {
  fetchData();
}
```

---

### **5. Combining Multiple Async Operations**
- **Description**: Use multiple `await` statements to perform sequential asynchronous operations.
- **Use Case**: Chain multiple asynchronous tasks.

#### Example:
```dart
Future<void> fetchData() async {
  print('Fetching user data...');
  await Future.delayed(Duration(seconds: 2)); // Simulate a network request
  print('User data fetched!');

  print('Fetching posts...');
  await Future.delayed(Duration(seconds: 1)); // Simulate another network request
  print('Posts fetched!');
}

void main() {
  fetchData();
}
```

**Output**:
```
Fetching user data...
User data fetched!
Fetching posts...
Posts fetched!
```

---

### **6. Example: Full Workflow**
Here’s an example of a complete workflow using `async` and `await`:

#### **Step 1: Define an Async Function**
```dart
Future<void> fetchData() async {
  print('Fetching data...');
  await Future.delayed(Duration(seconds: 2)); // Simulate a network request
  print('Data fetched!');
}
```

#### **Step 2: Call the Async Function**
```dart
void main() {
  fetchData();
  print('Fetching data in progress...');
}
```

#### **Step 3: Return a Value from an Async Function**
```dart
Future<String> fetchUserName() async {
  await Future.delayed(Duration(seconds: 2)); // Simulate a network request
  return 'John Doe';
}

void main() async {
  String userName = await fetchUserName();
  print('User: $userName'); // Output: User: John Doe
}
```

#### **Step 4: Handle Errors**
```dart
Future<void> fetchData() async {
  try {
    print('Fetching data...');
    await Future.delayed(Duration(seconds: 2)); // Simulate a network request
    throw Exception('Failed to fetch data'); // Simulate an error
  } catch (e) {
    print('Error: $e'); // Output: Error: Exception: Failed to fetch data
  }
}

void main() {
  fetchData();
}
```

#### **Step 5: Combine Multiple Async Operations**
```dart
Future<void> fetchData() async {
  print('Fetching user data...');
  await Future.delayed(Duration(seconds: 2)); // Simulate a network request
  print('User data fetched!');

  print('Fetching posts...');
  await Future.delayed(Duration(seconds: 1)); // Simulate another network request
  print('Posts fetched!');
}

void main() {
  fetchData();
}
```

---

### **Summary of Async/Await Features**
| Feature               | Description                              | Example                                   |
|-----------------------|------------------------------------------|-------------------------------------------|
| **Async Function**    | Mark a function as asynchronous          | `Future<void> fetchData() async { ... }`  |
| **Await**             | Wait for a `Future` to complete          | `await Future.delayed(Duration(seconds: 2))`|
| **Return Value**      | Return a value from an async function    | `return 'John Doe';`                      |
| **Error Handling**    | Handle errors with `try-catch`           | `try { ... } catch (e) { ... }`           |
| **Sequential Operations** | Combine multiple async operations    | `await operation1(); await operation2();` |

---

### **Example: Full Async/Await Workflow**
Here’s an example of a complete workflow using `async` and `await`:

#### **Step 1: Define an Async Function**
```dart
Future<void> fetchData() async {
  print('Fetching data...');
  await Future.delayed(Duration(seconds: 2)); // Simulate a network request
  print('Data fetched!');
}
```

#### **Step 2: Call the Async Function**
```dart
void main() {
  fetchData();
  print('Fetching data in progress...');
}
```

#### **Step 3: Return a Value from an Async Function**
```dart
Future<String> fetchUserName() async {
  await Future.delayed(Duration(seconds: 2)); // Simulate a network request
  return 'John Doe';
}

void main() async {
  String userName = await fetchUserName();
  print('User: $userName'); // Output: User: John Doe
}
```

#### **Step 4: Handle Errors**
```dart
Future<void> fetchData() async {
  try {
    print('Fetching data...');
    await Future.delayed(Duration(seconds: 2)); // Simulate a network request
    throw Exception('Failed to fetch data'); // Simulate an error
  } catch (e) {
    print('Error: $e'); // Output: Error: Exception: Failed to fetch data
  }
}

void main() {
  fetchData();
}
```

#### **Step 5: Combine Multiple Async Operations**
```dart
Future<void> fetchData() async {
  print('Fetching user data...');
  await Future.delayed(Duration(seconds: 2)); // Simulate a network request
  print('User data fetched!');

  print('Fetching posts...');
  await Future.delayed(Duration(seconds: 1)); // Simulate another network request
  print('Posts fetched!');
}

void main() {
  fetchData();
}
```

---

## Streams 

Here’s a summary of the **[Creating Streams in Dart](https://dart.dev/libraries/async/creating-streams)** documentation, using the same method you provided, with explanations and **code examples** where applicable:

---

### **Creating Streams in Dart**
Streams are a powerful feature in Dart for handling asynchronous data sequences. They allow you to process data as it becomes available, rather than waiting for all data to be ready.

---

### **1. What is a Stream?**
- **Description**: A stream is a sequence of asynchronous events. It can emit data, errors, and a "done" event when the stream is closed.
- **Use Case**: Handle real-time data, such as user input, network responses, or file I/O.

---

### **2. Creating a Stream**
- **Description**: Streams can be created using the `Stream` class or helper methods like `Stream.fromIterable` or `Stream.periodic`.
- **Use Case**: Generate a sequence of events programmatically.

#### Example: Using `Stream.fromIterable`
```dart
void main() async {
  // Create a stream from a list
  Stream<int> stream = Stream.fromIterable([1, 2, 3, 4, 5]);

  // Listen to the stream
  await for (int value in stream) {
    print(value); // Output: 1, 2, 3, 4, 5
  }
}
```

#### Example: Using `Stream.periodic`
```dart
void main() async {
  // Create a stream that emits a value every second
  Stream<int> stream = Stream.periodic(Duration(seconds: 1), (count) => count);

  // Listen to the stream (stop after 5 values)
  await for (int value in stream.take(5)) {
    print(value); // Output: 0, 1, 2, 3, 4
  }
}
```

---

### **3. Creating a Custom Stream**
- **Description**: Use the `StreamController` class to create and manage a custom stream.
- **Use Case**: Emit events manually and control the stream's behavior.

#### Example: Using `StreamController`
```dart
import 'dart:async';

void main() async {
  // Create a StreamController
  StreamController<int> controller = StreamController<int>();

  // Get the stream from the controller
  Stream<int> stream = controller.stream;

  // Listen to the stream
  stream.listen((value) {
    print('Received: $value');
  });

  // Add data to the stream
  controller.add(1);
  controller.add(2);
  controller.add(3);

  // Close the stream
  await controller.close();
}
```

**Output**:
```
Received: 1
Received: 2
Received: 3
```

---

### **4. Adding Error and Done Events**
- **Description**: Streams can emit errors and a "done" event when they are closed.
- **Use Case**: Handle errors and cleanup when the stream completes.

#### Example: Adding Errors and Done Events
```dart
import 'dart:async';

void main() async {
  StreamController<int> controller = StreamController<int>();

  Stream<int> stream = controller.stream;

  stream.listen(
    (value) => print('Received: $value'),
    onError: (error) => print('Error: $error'),
    onDone: () => print('Stream closed'),
  );

  controller.add(1);
  controller.addError('Something went wrong');
  controller.add(2);
  await controller.close();
}
```

**Output**:
```
Received: 1
Error: Something went wrong
Received: 2
Stream closed
```

---

### **5. Example: Full Workflow**
Here’s an example of a complete workflow for creating and using streams:

#### **Step 1: Create a Stream with `Stream.fromIterable`**
```dart
void main() async {
  Stream<int> stream = Stream.fromIterable([1, 2, 3, 4, 5]);

  await for (int value in stream) {
    print(value); // Output: 1, 2, 3, 4, 5
  }
}
```

#### **Step 2: Create a Stream with `Stream.periodic`**
```dart
void main() async {
  Stream<int> stream = Stream.periodic(Duration(seconds: 1), (count) => count);

  await for (int value in stream.take(5)) {
    print(value); // Output: 0, 1, 2, 3, 4
  }
}
```

#### **Step 3: Create a Custom Stream with `StreamController`**
```dart
import 'dart:async';

void main() async {
  StreamController<int> controller = StreamController<int>();

  Stream<int> stream = controller.stream;

  stream.listen((value) {
    print('Received: $value');
  });

  controller.add(1);
  controller.add(2);
  controller.add(3);

  await controller.close();
}
```

#### **Step 4: Add Error and Done Events**
```dart
import 'dart:async';

void main() async {
  StreamController<int> controller = StreamController<int>();

  Stream<int> stream = controller.stream;

  stream.listen(
    (value) => print('Received: $value'),
    onError: (error) => print('Error: $error'),
    onDone: () => print('Stream closed'),
  );

  controller.add(1);
  controller.addError('Something went wrong');
  controller.add(2);
  await controller.close();
}
```

---

### **Summary of Stream Features**
| Feature               | Description                              | Example                                   |
|-----------------------|------------------------------------------|-------------------------------------------|
| **Stream.fromIterable** | Create a stream from a list            | `Stream.fromIterable([1, 2, 3])`         |
| **Stream.periodic**   | Create a stream that emits values periodically | `Stream.periodic(Duration(seconds: 1), (count) => count)` |
| **StreamController**  | Create and manage a custom stream       | `StreamController<int>()`                 |
| **Error Handling**    | Handle errors in a stream               | `stream.listen(..., onError: (error) { ... })` |
| **Done Event**        | Handle the stream's completion          | `stream.listen(..., onDone: () { ... })`  |

---

### **Example: Full Stream Workflow**
Here’s an example of a complete workflow for creating and using streams:

#### **Step 1: Create a Stream with `Stream.fromIterable`**
```dart
void main() async {
  Stream<int> stream = Stream.fromIterable([1, 2, 3, 4, 5]);

  await for (int value in stream) {
    print(value); // Output: 1, 2, 3, 4, 5
  }
}
```

#### **Step 2: Create a Stream with `Stream.periodic`**
```dart
void main() async {
  Stream<int> stream = Stream.periodic(Duration(seconds: 1), (count) => count);

  await for (int value in stream.take(5)) {
    print(value); // Output: 0, 1, 2, 3, 4
  }
}
```

#### **Step 3: Create a Custom Stream with `StreamController`**
```dart
import 'dart:async';

void main() async {
  StreamController<int> controller = StreamController<int>();

  Stream<int> stream = controller.stream;

  stream.listen((value) {
    print('Received: $value');
  });

  controller.add(1);
  controller.add(2);
  controller.add(3);

  await controller.close();
}
```

#### **Step 4: Add Error and Done Events**
```dart
import 'dart:async';

void main() async {
  StreamController<int> controller = StreamController<int>();

  Stream<int> stream = controller.stream;

  stream.listen(
    (value) => print('Received: $value'),
    onError: (error) => print('Error: $error'),
    onDone: () => print('Stream closed'),
  );

  controller.add(1);
  controller.addError('Something went wrong');
  controller.add(2);
  await controller.close();
}
```

---

## Futures and Error Handling 

Here’s a summary of the **[Futures and Error Handling in Dart](https://dart.dev/libraries/async/futures-error-handling)** documentation, using the same method you provided, with explanations and **code examples** where applicable:

---

### **Futures and Error Handling in Dart**
Futures represent asynchronous computations that may complete with a value or an error. Proper error handling is essential to ensure your app behaves predictably when something goes wrong.

---

### **1. What is a Future?**
- **Description**: A `Future` represents a potential value or error that will be available at some time in the future.
- **Use Case**: Perform asynchronous operations like network requests, file I/O, or database queries.

---

### **2. Handling Errors in Futures**
- **Description**: Use `try-catch` blocks or the `catchError` method to handle errors in asynchronous code.
- **Use Case**: Gracefully handle exceptions that occur during asynchronous operations.

#### Example: Using `try-catch` with `await`
```dart
Future<void> fetchData() async {
  try {
    print('Fetching data...');
    await Future.delayed(Duration(seconds: 2)); // Simulate a network request
    throw Exception('Failed to fetch data'); // Simulate an error
  } catch (e) {
    print('Error: $e'); // Output: Error: Exception: Failed to fetch data
  }
}

void main() {
  fetchData();
}
```

#### Example: Using `catchError`
```dart
Future<void> fetchData() {
  return Future.delayed(Duration(seconds: 2))
      .then((_) {
        throw Exception('Failed to fetch data'); // Simulate an error
      })
      .catchError((error) {
        print('Error: $error'); // Output: Error: Exception: Failed to fetch data
      });
}

void main() {
  fetchData();
}
```

---

### **3. Chaining Futures**
- **Description**: Use `then` to chain multiple asynchronous operations and `catchError` to handle errors in the chain.
- **Use Case**: Perform sequential asynchronous tasks.

#### Example: Chaining Futures
```dart
Future<void> fetchData() {
  return Future.delayed(Duration(seconds: 2))
      .then((_) {
        print('Data fetched!');
        throw Exception('Failed to process data'); // Simulate an error
      })
      .then((_) {
        print('This will not be executed');
      })
      .catchError((error) {
        print('Error: $error'); // Output: Error: Exception: Failed to process data
      });
}

void main() {
  fetchData();
}
```

---

### **4. Example: Full Workflow**
Here’s an example of a complete workflow for handling errors in futures:

#### **Step 1: Using `try-catch` with `await`**
```dart
Future<void> fetchData() async {
  try {
    print('Fetching data...');
    await Future.delayed(Duration(seconds: 2)); // Simulate a network request
    throw Exception('Failed to fetch data'); // Simulate an error
  } catch (e) {
    print('Error: $e'); // Output: Error: Exception: Failed to fetch data
  }
}

void main() {
  fetchData();
}
```

#### **Step 2: Using `catchError`**
```dart
Future<void> fetchData() {
  return Future.delayed(Duration(seconds: 2))
      .then((_) {
        throw Exception('Failed to fetch data'); // Simulate an error
      })
      .catchError((error) {
        print('Error: $error'); // Output: Error: Exception: Failed to fetch data
      });
}

void main() {
  fetchData();
}
```

#### **Step 3: Chaining Futures**
```dart
Future<void> fetchData() {
  return Future.delayed(Duration(seconds: 2))
      .then((_) {
        print('Data fetched!');
        throw Exception('Failed to process data'); // Simulate an error
      })
      .then((_) {
        print('This will not be executed');
      })
      .catchError((error) {
        print('Error: $error'); // Output: Error: Exception: Failed to process data
      });
}

void main() {
  fetchData();
}
```

---

### **Summary of Futures and Error Handling Features**
| Feature               | Description                              | Example                                   |
|-----------------------|------------------------------------------|-------------------------------------------|
| **try-catch with await** | Handle errors in async functions       | `try { ... } catch (e) { ... }`           |
| **catchError**        | Handle errors in chained futures        | `.catchError((error) { ... })`            |
| **Chaining Futures**  | Perform sequential async tasks          | `.then((_) { ... }).catchError((error) { ... })` |

---

### **Example: Full Futures and Error Handling Workflow**
Here’s an example of a complete workflow for handling errors in futures:

#### **Step 1: Using `try-catch` with `await`**
```dart
Future<void> fetchData() async {
  try {
    print('Fetching data...');
    await Future.delayed(Duration(seconds: 2)); // Simulate a network request
    throw Exception('Failed to fetch data'); // Simulate an error
  } catch (e) {
    print('Error: $e'); // Output: Error: Exception: Failed to fetch data
  }
}

void main() {
  fetchData();
}
```

#### **Step 2: Using `catchError`**
```dart
Future<void> fetchData() {
  return Future.delayed(Duration(seconds: 2))
      .then((_) {
        throw Exception('Failed to fetch data'); // Simulate an error
      })
      .catchError((error) {
        print('Error: $error'); // Output: Error: Exception: Failed to fetch data
      });
}

void main() {
  fetchData();
}
```

#### **Step 3: Chaining Futures**
```dart
Future<void> fetchData() {
  return Future.delayed(Duration(seconds: 2))
      .then((_) {
        print('Data fetched!');
        throw Exception('Failed to process data'); // Simulate an error
      })
      .then((_) {
        print('This will not be executed');
      })
      .catchError((error) {
        print('Error: $error'); // Output: Error: Exception: Failed to process data
      });
}

void main() {
  fetchData();
}
```

---

