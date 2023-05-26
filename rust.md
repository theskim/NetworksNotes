# Rust Programming Language

## Overview
- Rust is a systems programming language known for its focus on safety, speed, and concurrency.
- It provides modern language features while maintaining low-level control over hardware resources.

## Basic Syntax
- Variables are immutable by default but can be made mutable with the `mut` keyword.
- Rust uses snake_case for variable and function names.
- Statements are terminated with a semicolon `;`.
```
let x = 5;
let mut y = 10;
```

## Loops
- Rust provides different types of loops:
  - `loop`: Runs a block of code repeatedly until explicitly stopped.
  - `while`: Executes a block of code as long as a condition is true.
  - `for`: Iterates over a collection or a range of values.
```
loop {
    // Code here
    if condition {
        break; // Exit the loop
    }
}

let mut i = 0;
while i < 5 {
    // Code here
    i += 1;
}

for x in 0..5 {
    // Code here
}
```

## Ownership
- Rust follows the ownership model, where each value has a variable that owns it.
- Ownership allows Rust to manage memory and prevent issues like dangling pointers and data races.

### Ownership Transfer
- Ownership of a value can be transferred from one variable to another using a move.
- After the transfer, the original variable becomes invalid to prevent multiple ownership.

```
let s1 = String::from("Hello");
let s2 = s1; // Ownership transferred to s2
println!("{}", s2); // Ownership transferred, s1 is invalid
```

### Borrowing
- Borrowing allows temporary access to a value without transferring ownership.
- Multiple immutable borrows are allowed, but only one mutable borrow can exist in a particular scope.
```
fn print_length(s: &str) {
    println!("Length: {}", s.len());
}

let message = String::from("Hello, Rust!");
print_length(&message); // Borrowing the value without ownership transfer
```

### Ownership and Functions
- When a value is passed to a function, ownership may be transferred unless borrowing is used.
- Functions can return ownership back to the caller using the return keyword.
```
fn create_greeting() -> String {
    let greeting = String::from("Hello, Rust!");
    greeting // Ownership transferred to the caller
}

let message = create_greeting(); // Ownership received from the function
println!("{}", message);
```

### References and Lifetimes
- References are a way to refer to values without taking ownership.
- References have lifetimes, which ensure that the borrowed value remains valid.
```
fn get_length(s: &str) -> usize {
    s.len()
}

let message = String::from("Hello, Rust!");
let length = get_length(&message); // Borrowing the value without ownership transfer
println!("Length: {}", length);
```

## References
- References in Rust allow borrowing values without taking ownership.
- They are a way to refer to a value without moving or copying it.
- References are used to pass values to functions without transferring ownership or to enable multiple immutable references to the same data.

### Immutable References
- Immutable references, denoted by the `&` symbol, allow read-only access to the borrowed value.
- Multiple immutable references can exist simultaneously.
- Immutable references prevent mutation of the borrowed value.

```
fn print_length(s: &str) {
    println!("Length: {}", s.len());
}

let message = "Hello, Rust!";
print_length(&message);
```

### Mutable References
- Mutable references, denoted by &mut, allow read and write access to the borrowed value.
- Only one mutable reference can exist in a particular scope.
- Mutable references enable modifying the borrowed value.
```
fn capitalize(s: &mut String) {
    s.make_ascii_uppercase();
}

let mut message = String::from("hello");
capitalize(&mut message);
println!("{}", message);
```

## Option Type
- The `Option` type is used to handle scenarios where a value may or may not be present.
- It is often used to represent the possibility of a value being `Some(value)` or the absence of a value `None`.
- It helps avoid null pointer errors by enforcing explicit handling of possible absence.
```
let some_value: Option<i32> = Some(5);
let no_value: Option<i32> = None;

match some_value {
    Some(value) => println!("Value: {}", value),
    None => println!("No value"),
}
```

## Result Type
- The `Result` type is used to handle operations that can produce either a successful value or an error.
- It is often used to represent the possibility of a result being `Ok(value)` or an error being `Err(error)`.
- It helps enforce explicit error handling and propagation.

```
fn divide(x: f64, y: f64) -> Result<f64, String> {
    if y != 0.0 {
        Ok(x / y)
    } else {
        Err(String::from("Cannot divide by zero."))
    }
}

match divide(10.0, 2.0) {
    Ok(result) => println!("Result: {}", result),
    Err(error) => println!("Error: {}", error),
}
```

## Containers
Rust provides several built-in container types in its standard library:

### Vector (Vec)
- A dynamic-size array that can grow or shrink.
- Elements are stored sequentially in memory.
- Allows efficient access, insertion, and removal of elements.

```
let mut numbers: Vec<i32> = Vec::new();
numbers.push(1);
numbers.push(2);
numbers.push(3);

for number in &numbers {
    println!("{}", number);
}
```

## Advanced Syntax
- Pattern matching: Allows matching values against patterns to execute different code based on the pattern.
- Structs: Used to create custom data types with named fields (Similar to C++).
- Enums: Define a type by enumerating its possible variants.
- Traits: Define shared behavior across types.
- Error handling: Rust provides the `Result` type and the `match` keyword for error handling.
- Generics: Enable writing code that can work with multiple types.
- Closures: Anonymous functions that can capture values from their environment.
- Concurrency: Rust provides concurrency primitives like threads and message passing.

```
match value {
    1 => println!("One"),
    2 => println!("Two"),
    _ => println!("Other"),
}

struct Point {
    x: i32,
    y: i32,
}

enum Result<T, E> {
    Ok(T),
    Err(E),
}

trait Printable {
    fn print(&self);
}

impl Printable for i32 {
    fn print(&self) {
        println!("Value: {}", *self);
    }
}

fn main() {
    let result: Result<i32, String> = Ok(5);
    match result {
        Ok(value) => value.print(),
        Err(err) => println!("Error: {}", err),
    }
}
```

## String
- The String type represents an owned, mutable, growable text string.
- It is a heap-allocated, resizable, UTF-8 encoded string.
- Provides ownership and full control over the string data.
- Supports various string manipulation operations.
- Useful when you need to modify or concatenate strings dynamically.

```
let mut message = String::from("Hello");
message.push_str(", World!");

println!("{}", message);
```

## str (String Slice)
- The str type, also known as string slice, represents an immutable sequence of UTF-8 encoded characters.
- It is a borrowed reference to a portion of a String or a string literal.
- Cannot be modified or grow in size.
- Allows read-only access to the underlying string data.
- Useful when you need to work with string data without modifying it.
```
fn print_greeting(name: &str) {
    println!("Hello, {}!", name);
}

let name = "Alice";
print_greeting(name);
```
- In the example above, name is of type &str, which is a reference to a string literal.
The print_greeting function takes a parameter of type &str and prints a greeting message.
- String literals have the type &'static str, where 'static refers to the lifetime of the string literal, which is 'static or 'global.
- String slices can also be obtained from String types using the & operator.

## Array
- An array is a fixed-size, homogenous collection of elements in Rust.
- All elements in an array must have the same data type.
- Arrays have a fixed length defined at compile-time and cannot grow or shrink.
- Accessing elements in an array is fast, as they are stored sequentially in memory.
```
let numbers: [i32; 5] = [1, 2, 3, 4, 5];

println!("Third number: {}", numbers[2]);

for number in &numbers {
    println!("{}", number);
}
```

## Hash Map
- The Hash Map is a collection type in Rust that stores a set of key-value pairs.
- It is implemented as a hash table, providing fast lookup and efficient insertion and deletion.
- Keys in a hash map must be unique.
- Values can be of any type.
- Hash maps are useful when you need to associate values with specific keys and quickly retrieve them.

```
use std::collections::HashMap;

let mut scores = HashMap::new();

scores.insert("Alice", 100);
scores.insert("Bob", 85);
scores.insert("Charlie", 90);

if let Some(score) = scores.get("Alice") {
    println!("Alice's score: {}", score);
}

for (name, score) in &scores {
    println!("{}: {}", name, score);
}
```