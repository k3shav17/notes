# TypeScript

**TypeScript**: It is a superset of JavaScript. TypeScript supports everything that Javascript supports and more.

- TS also supports classes, interfaces and some other functional which makes using JS easy.
- TS is mostly nothing but statically typed JS.
- As JS is dynamically typed language, we face many challenges with type safety of the variables or the stuff we use in JS.
- Where as TS allows us to explicitly mention the type of the variable.

:exclaimation:And ultimately the TS file is compiled or transpiled into JS because browsers only support JS. The process of compiling a TS file is called Transpilation.

TS is a statically typed JS, where we explicitly mention the type of the variable that is declared. TS provides a type called 'any' which takes any datatype same as JS. This any type have subtypes, those are, Primitive types, Object types and Parameter types.

- Primitive types are ... Boolean, string, number, symbol, null, undefined
- Object types are ... class, interface, arrays and literals

TS supports features that are not even a thing in JS, that is why TS is a superset of JS. TS also supports enum (as of now I don't know whether JS supports enum or not), interfaces and classes.

**Interfaces** in TS are similar to that of interfaces in OOP.

- Interfaces in TS are a powerful way of defining 'code contract' with your code and as well as code outside of your project.
- Interfaces doesnot initialize or implement the properties that are declared in it. The only job of an interface is to describe a type.
- Interfaces doesnot have any runtime representation, they are purely compile time constructs.
- Interfaces are mainly useful for documenting and validating the type of the parameters that are declared inside the interface when that interface is used as a type for an object.
- This enables us to catch error and to check whether the data that we are passing is of right type or not and this happens at compile time not at the time of run.

syntax to declare interface in TS is

```Ts
interface InterfaceName {

  variable properties or methods can be declared here

 }
 ```

## How is interfaces are different from type alias?

- Type alias is a definition of a type of data. We can only describe a union or tuple using type alias.
- where as on the other hand interfaces are a way to describe the shape of the properties like objects.
- Using a type is as same as interface, but interfaces are extendible, and types or not.

We can extend and interface in TS same as in Java, but whenever an interface extends another interface and if we implement the child interface then all the required properties of all interfaces needs to be implemented.

- What is the difference between type any and type unknown?

 > The major difference between these types are, for the type 'any' the properties of type any can be accessed and we can call or construct them, this not the case with of type unknown.

 > **Functions in TypeScript**
 In java script function parameters do not specify parameter types, or type checking or the number of parameters received. TS solves the problem by allowing us to specify the type in the parameters and the return type of the function.

 >**Named Functions.**
Named functions are the functions that are declared with function keyword and a distinguishable name within the current scope. These functions are loaded in to the execution even before the code runs, and we can use the function even before it is declared, this feature is called Hoisting.

 ```ts
 function simpleFunction() {

  return something;
 }
 ```

 > **Anonymous functions.**

- Anonymous functions are the functions that has no name. These functions are also called as function expressions and these functions do not support Hoisting feature, because these functions are not loaded into the execution context, and runs only when the code encounters it.

```ts
  let someFunction = function () {

   return something;
 }
```

 >**Arrow Functions**

- These functions are similar to lambda functions in Java.
