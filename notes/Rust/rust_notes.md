# Rust

Rust is a general purpose, multi-paradigm, system programming language which mainly concentrates on performance and fearless, safety concurrency. It cares a lot about the size of the values in memory, whether things can be modified or not.

Rust is able to identify the type of the variable based on the value passed.

- We can explicitly mention the type of the variable at the time of declaration.

*variable shadowing* - is technique where we can assign values to same variable names multiple times.

- variable names should be **snake_case**.

If we want a variable to be read-write then it should be declared with *mut* keyword.

 ``` Rust
   let mut variable = 10;
   ```

## Primitive Types

- bool => true/false

- un-signed integer => u8, u16..u128 (for non negative whole numbers).

- signed integers => i8..i128

- pointer sized => usize, isize (to specify the size of the pointers).

- floats - f32, f64

- tuple - (value, value, ...) for passing fixed sequences of values on the stack.

- arrays - [value, value, ...] collection of similar data types, whose length will be known at compile time.

- slices - a collection of similar elements with length known at runtime.

## Type conversion

- We cannot use a **u8** with a **u32**, if does, then it will throws an error.
- Rust provides a keywords called **as**, which helps to convert the type of the variable.

- **Constants**

- Constants allow us to specify a common value which can be used thorughout the code many times. Constants always needs to be declared explicitly.
- Constants can be declared as

```Rust
const THIS_IS_A_CONST: f32 = 10;
```

***Arrays***

- An array is a fixed length collection of similar elements whose size is defined at compile time.

- Arrays can be declared as

> ```let array: [T; N]``` where T is type and N is size. ```let nums: [i32; 3] = [1, 2, 3];```

## Functions

- A function has 0 or more parameters.

- If I define a function named *add(x: i32, y: i32)* then the values in the paranthese are called parameters.
- And if I am calling this method from another scope then the values that I needed to be passed are called arguments.

- Function names are always **snake_case();**.

- Example

```Rust
fn add(x: i32, y: i32) -> i32 {
return x + y;
}

fn subtract(x: i32, y: i32) -> i32 {
x - y
}

fn main() {
println!("42 + 13 = {}", add(42, 13));
println!("42 - 13 = {}", subtract(42, 13));
}
```

- Functions can return multiple values by returning **tuple()**. Tuple can be referenced by it's index number.

- An empty tuple will be returned if no return type is specified for a function. Empty tuple can be represented as **()**.

## Conditionals

- **For** in rust is based on ***iterator()*** concept, where an iterator is an object, in which we can ask "what is the next item?", until there are none.

- **..,  ..=** operators are equivalent to **<, <=** in java conditional statements.

```Rust
fn main() {
    for x in 0..5 {
        println!("{}", x);
    }
    println!("\n");
    for x in 0..=5 {
        println!("{}", x);
    }
}

```

- ### match

- **match** is similar to **switch** in java.

```Rust
fn main() {
    
    let x = 42;

    match x {
        0 => {
            println!("found zero");
        }
        // we can match against multiple values
        1 | 2 => {
            println!("found 1 or 2!");
        }
        // we can match against ranges
        3..=9 => {
            println!("found a number 3 to 9 inclusively");
        }
        // we can bind the matched number to a variable
        matched_num @ 10..=100 => {
            println!("found {} number between 10 to 100!", matched_num);
        }
        // this is the default match that must exist if not all cases are handled
        _ => {
            println!("found something else!");
        }
    }
}
```

### Tuple

- Tuple is similar to array but can have different types of datatypes.
- An empty tuple **()** is known as unit.

### Sturcts

- It is a type composed of other types, and can contain different types.

- Types

1. Classic -> most commanly used, where each field will be having a name and type.
2. Tuple -> Similar to classic structs, but their fields won't have names.
3. Unit -> Have not fields, just an empty tuple **()**.

- **struct** keyword is used to define a custom struct, and the name should describe the object appropriately.

```Rust
struct Car {
    make: String,
    model: String,
    year: u32,
}
```

## **Ownership**

1. Each value in Rust has a variable that's called its owner.
2. There can be only one owner at a time.
3. When the owner goes out of scope, the value will be dropped.

```Rust
{ s is not valid here, it is not yet declared.
    let s: &str = "hello"; -> s is valid from this point.
    do something with s
} this scope is now over, and s is no longer valid.
```

```Rust
1. let s: &str = "hello"; is a string literal and will be stored in binary.

2. If we want a dynamic string then we have declare as follow.

 let s: String = "hello"; is a dynamic string which can be mutated and will be stored in the heap.
```

```Rust
 let x = 5;
    let y = x; // Here the value of x being copied to y
    println!("The values of x and y {}, {}", x, y);

    let first = String::from("hello");
    let second = first; // in here the value of first is being moved to the second variable not copied.
                        // println!("first values is {}", first); // here we cannot print the value of first because it got moved to another variable.
    println!("strings first and second {}", second);

    // to clone the value of string to another variable, we have to invoke the clone method.
    let third = second.clone();
    println!("The valued of third is {}", third);
```

> Basically integers are copied and dynamic Strings are get moved.[Reference for Ownership](https://github.com/k3shav17/Code/blob/main/Rust/ownership/src/main.rs)

## Rules of References

- At any given time, you can have either one mutable reference or any number of immutable reference.
- References must always be valid.
