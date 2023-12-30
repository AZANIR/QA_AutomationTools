# TypeScript Best Practices for Improved Code Quality

_Content_

[Intro](#intro)

[Strict Type Checking](#best-practice-1-strict-type-checking)

[Type Inference](#best-practice-2-type-inference)

[Linters](#best-practice-3-linters)

[Interfaces](#best-practice-4-interfaces)

[Type Aliases](#best-practice-5-type-aliases)

[Using Tuples](#best-practice-6-using-tuples)

[Using any Type](#best-practice-7-using-any-type)

[Using the unknown Type](#best-practice-8-using-the-unknown-type)

[“never”](#best-practice-9-never)

[Using the keyof operator](#best-practice-10-using-the-keyof-operator)

[Using Enums](#best-practice-11-using-enums)

[Using Namespaces](#best-practice-12-using-namespaces)

[Using Utility Types](#best-practice-13-using-utility-types)

[“Readonly” and “ReadonlyArray”](#best-practice-14-readonly-and-readonlyarray)

[Type Guards](#best-practice-15-type-guards)

[Using Generics](#best-practice-16-using-generics)

[Using the infer keyword](#best-practice-17-using-the-infer-keyword)

[Using Conditional Types](#best-practice-18-using-conditional-types)

[Using Mapped Types](#best-practice-19-using-mapped-types)

[Using Decorators](#best-practice-20-using-decorators)

## Intro

TypeScript is a widely used, open-source programming language that is perfect for modern development. With its advanced type system, TypeScript allows developers to write code that is more robust, maintainable, and scalable. But, to truly harness the power of TypeScript and build high-quality projects, it’s essential to understand and follow best practices. In this article, we’ll dive deep into the world of TypeScript and explore 20 best practices for mastering the language. These best practices cover a wide range of topics and provide concrete examples of how to apply them in real-world projects. Whether you’re just starting out or you’re an experienced TypeScript developer, this article will provide valuable insights and tips to help you write clean, efficient code.

## Best Practice 1: Strict Type Checking

We will start with the most basic ones. Imagine being able to catch potential errors before they even happen, sounds too good to be true? Well, that’s exactly what strict type checking in TypeScript can do for you. This best practice is all about catching those sneaky bugs that can slip into your code and cause headaches down the line.

Strict type checking is all about making sure that the types of your variables match the types you expect them to be. This means that if you declare a variable to be of type string, TypeScript will make sure that the value assigned to that variable is indeed a string and not a number, for example. This helps you to catch errors early on and make sure your code is working as intended.
Enabling strict type checking is as simple as adding “strict”: true to your tsconfig.json file (has to be true by default). By doing this, TypeScript will enable a set of checks that will catch certain errors that would otherwise go unnoticed.

Here’s an example of how strict type checking can save you from a common mistake:

```typescript
let userName: string = "John";
userName = 123; // TypeScript will raise an error because "123" is not a string.
```

By following this best practice, you will be able to catch errors early on and make sure that your code is working as intended, saving you time and frustration in the long run.

## Best Practice 2: Type Inference

TypeScript is all about being explicit with your types, but that doesn’t mean you have to spell everything out.

Type inference is the ability of the TypeScript compiler to automatically determine the type of a variable based on the value that is assigned to it. This means that you don’t have to explicitly specify the type of a variable every time you declare it. Instead, the compiler will look at the value and infer the type for you.

For example, in the following code snippet, TypeScript will automatically infer that the type of name is a string:

```typescript
let name = "John";
```

Type inference is especially useful when you are working with complex types or when you are initializing a variable with a value that is returned from a function.

But remember, type inference is not a magic wand, sometimes it’s better to be explicit with types, especially when working with complex types or when you want to make sure that a specific type is used.

## Best Practice 3: Linters

Linters are tools that can help you to write better code by enforcing a set of rules and guidelines. They can help you to catch potential errors and improve the overall quality of your code.

There are several linters available for TypeScript, such as TSLint and ESLint, that can help you to enforce a consistent code style and catch potential errors. These linters can be configured to check for things like missing semicolons, unused variables, and other common issues.

## Best Practice 4: Interfaces

When it comes to writing clean and maintainable code, interfaces are your best friend. They are like a blueprint for your objects, outlining the structure and properties of the data you will be working with.

An interface in TypeScript defines a contract for the shape of an object. It specifies the properties and methods that an object of that type should have, and it can be used as a type for a variable. This means that when you assign an object to a variable with an interface type, TypeScript will check that the object has all the properties and methods specified in the interface.

Here’s an example of how to define and use an interface in TypeScript:
    
```typescript
interface User {
name: string;
age: number;
}
let user: User = {name: "John", age: 25};
```

Interfaces also make it easier to refactor your code, by ensuring that all the places where a certain type is used are updated at once.

## Best Practice 5: Type Aliases

TypeScript allows you to create custom types using a feature called type aliases. The main difference between features type alias and interfaceis that type alias creates a new name for the type, whereas interface creates a new name for the shape of the object.

For example, you can use a type alias to create a custom type for a point in a two-dimensional space:

```typescript
type Point = { x: number, y: number };
let point: Point = { x: 0, y: 0 };
```

Type aliases can also be used to create complex types, such as a union type or an intersection type.

```typescript
type User = { name: string, age: number };
type Admin = { name: string, age: number, privileges: string[] };
type SuperUser = User & Admin;
```

## Best Practice 6: Using Tuples

Tuples are a way to represent a fixed-size array of elements with different types. They allow you to express a collection of values with a specific order and types.

For example, you can use a tuple to represent a point in a 2D space:

```typescript
let point: [number, number] = [1, 2];
```

You can also use a tuple to represent a collection of multiple types:

```typescript
let user: [string, number, boolean] = ["Bob", 25, true];
```

One of the main advantages of using tuples is that they provide a way to express a specific type relationship between the elements in the collection.

In addition, you can use destructuring assignment to extract the elements of a tuple and assign them to variables:

```typescript
let point: [number, number] = [1, 2];
let [x, y] = point;
console.log(x, y);
```

## Best Practice 7: Using any Type

Sometimes, we may not have all the information about a variable’s type, but still need to use it in our code. In such cases, we can utilize the any type. But, like any powerful tool, the use of any should be used with caution and purpose.

One best practice when using any is to limit its usage to specific cases where the type is truly unknown, such as when working with third-party libraries or dynamically generated data. Additionally, it’s a good idea to add type assertions or type guards to ensure the variable is being used correctly. And when possible, try to narrow down the type of the variable as much as you can.

For example:

```typescript
function logData(data: any) {
console.log(data);
}

const user = { name: "John", age: 30 };
const numbers = [1, 2, 3];

logData(user); // { name: "John", age: 30 }
logData(numbers); // [1, 2, 3]
```

Another best practice is to avoid using any in function return types and function arguments, as it can weaken the type safety of your code. Instead, you can use a type that is more specific or use a type that is more general like unknown or object that still provide some level of type safety.

## Best Practice 8: Using the unknown Type

The unknown type is a powerful and restrictive type that was introduced in TypeScript 3.0. It is a more restrictive type than any and it can help you to prevent unintended type errors.
Unlike any, when you use the unknown type, TypeScript will not allow you to perform any operation on a value unless you first check its type. This can help you to catch type errors at compile-time, instead of at runtime.

For example, you can use the unknown type to create a more type-safe function:

```typescript
function printValue(value: unknown) {
if (typeof value === "string") {
console.log(value);
} else {
console.log("Not a string");
}
}
```

You can also use the unknown type to create more type-safe variables:

```typescript
let value: unknown = "hello";
let str: string = value; // Error: Type 'unknown' is not assignable to type 'string'.
```

## Best Practice 9: “never”

In TypeScript, never is a special type that represents values that will never occur. It’s used to indicate that a function will not return normally, but will instead throw an error. This is a great way to indicate to other developers (and the compiler) that a function can’t be used in certain ways, this can help to catch potential bugs.

For example, consider the following function that throws an error if the input is less than 0:

```typescript
function divide(numerator: number, denominator: number): number {
if (denominator === 0) {
throw new Error("Cannot divide by zero");
}
return numerator / denominator;
}
```

Here, the function divide is declared to return a number, but if the denominator is zero, it will throw an error. To indicate that this function will not return normally in this case, you can use never as the return type:

```typescript
function divide(numerator: number, denominator: number): number | never {
if (denominator === 0) {
throw new Error("Cannot divide by zero");
}
return numerator / denominator;
}
```

## Best Practice 10: Using the keyof operator

The keyof operator is a powerful feature of TypeScript that allows you to create a type that represents the keys of an object. It can be used to make it clear which properties are allowed for an object.

For example, you can use the keyof operator to create a more readable and maintainable type for an object:

```typescript
interface User {
name: string;
age: number;
}

type UserKeys = keyof User; // "name" | "age"
```

You can also use the keyof operator to create more type-safe functions that take an object and a key as arguments:

```typescript
function getValue<T, K extends keyof T>(obj: T, key: K) {
return obj[key];
}
let user: User = { name: "John", age: 30 };
console.log(getValue(user, "name")); // "John"
console.log(getValue(user, "gender")); // Error: Argument of type '"gender"' is not assignable to parameter of type '"name" | "age"'.
```

## Best Practice 11: Using Enums

Enums, short for enumerations, are a way to define a set of named constants in TypeScript. They can be used to create a more readable and maintainable code, by giving a meaningful name to a set of related values.

For example, you can use an enum to define a set of possible status values for an order:

```typescript
enum OrderStatus {
Pending,
Processing,
Shipped,
Delivered,
Cancelled
}

let orderStatus: OrderStatus = OrderStatus.Pending;
```

Enums can also have a custom set of numeric values or strings.

```typescript
enum OrderStatus {
Pending = 1,
Processing = 2,
Shipped = 3,
Delivered = 4,
Cancelled = 5
}

let orderStatus: OrderStatus = OrderStatus.Pending;
```

Always name an enum with the first capital letter and the name has to be in singular form, as a part of the naming convention.

## Best Practice 12: Using Namespaces

Namespaces are a way to organize your code and prevent naming collisions. They allow you to create a container for your code, where you can define variables, classes, functions, and interfaces.

For example, you can use a namespace to group all the code related to a specific feature:

```typescript
namespace OrderModule {
export class Order { /_ … _/ }
export function cancelOrder(order: Order) { /_ … _/ }
export function processOrder(order: Order) { /_ … _/ }
}
let order = new OrderModule.Order();
OrderModule.cancelOrder(order);
```

You can also use namespaces to prevent naming collisions by providing a unique name for your code:

```typescript
namespace MyCompany.MyModule {
export class MyClass { /_ … _/ }
}

let myClass = new MyCompany.MyModule.MyClass();
```

It’s important to note that namespaces are similar to modules, but they are used to organize the code and prevent naming collisions, while modules are used to load and execute the code.

## Best Practice 13: Using Utility Types

Utility types are a built-in feature of TypeScript that provide a set of predefined types to help you write better type-safe code. They allow you to perform common type operations and manipulate types in a more convenient way.

For example, you can use the Pick utility type to extract a subset of properties from an object type:

```typescript
type User = { name: string, age: number, email: string };
type UserInfo = Pick<User, "name" | "email">;
```

You can also use the Exclude utility type to remove properties from an object type:

```typescript
type User = { name: string, age: number, email: string };
type UserWithoutAge = Exclude<User, "age">;
```

You can use the Partial utility type to make all properties of a type optional:

```typescript
type User = { name: string, age: number, email: string };
type PartialUser = Partial<User>;
```

## Best Practice 14: “Readonly” and “ReadonlyArray”

When working with data in TypeScript, you might want to make sure that certain values can’t be changed. And that’s where Readonly and ReadonlyArray come in.

The Readonly keyword is used to make properties of an object read-only, meaning they can’t be modified after they are created. 

This can be useful when working with configuration or constant values, for example.

```typescript
interface Point {
x: number;
y: number;
}
let point: Readonly<Point> = {x: 0, y: 0};
point.x = 1; // TypeScript will raise an error because "point.x" is read-only
```

The ReadonlyArray is similar to Readonly but for arrays. It makes an array read-only, and it can’t be modified after it’s created.

```typescript
let numbers: ReadonlyArray<number> = [1, 2, 3];
numbers.push(4); // TypeScript will raise an error because "numbers" is read-only
```

## Best Practice 15: Type Guards

When working with complex types in TypeScript, it can be challenging to keep track of the different possibilities of a variable. Type guards are a powerful tool that can help you to narrow down the type of a variable based on certain conditions.

Here’s an example of how to use a type guard to check if a variable is a number:

```typescript
function isNumber(x: any): x is number {
return typeof x === "number";
}
let value = 3;
if (isNumber(value)) {
value.toFixed(2); // TypeScript knows that "value" is a number because of the type guard
}
```

Type guards can also be used with the “in” operator, the typeof operator and the instanceof operator.

## Best Practice 16: Using Generics

Generics are a powerful feature of TypeScript that allows you to write code that can work with any type, making it more reusable. Generics allow you to write a single function, class or interface that can work with multiple types, without having to write separate implementations for each type.

For example, you can use a generic function to create an array of any type:

```typescript
function createArray<T>(length: number, value: T): Array<T> {
let result = [];

for (let i = 0; i < length; i++) {
result[i] = value;
}

return result;
}

let names = createArray<string>(3, "Bob");
let numbers = createArray<number>(3, 0);
```

You can also use generics to create a class that can work with any type of data:

```typescript
class GenericNumber<T> {
zeroValue: T;
add: (x: T, y: T) => T;
}

let myGenericNumber = new GenericNumber<number>();
myGenericNumber.zeroValue = 0;
myGenericNumber.add = function(x, y) { return x + y; };
```

## Best Practice 17: Using the infer keyword

The infer keyword is a powerful feature of TypeScript that allows you to extract the type of a variable in a type.

For example, you can use the infer keyword to create a more precise type for a function that returns an array of a specific type:

```typescript
type ArrayType<T> = T extends (infer U)[] ? U : never;
type MyArray = ArrayType<string[]>; // MyArray is of type string
```

You can also use the infer keyword to create more precise types for a function that returns an object with a specific property:

```typescript
type ObjectType<T> = T extends { [key: string]: infer U } ? U : never;
type MyObject = ObjectType<{ name: string, age: number }>; // MyObject is of type {name:string, age: number}
```

## Best Practice 18: Using Conditional Types

Conditional types let you to express more complex type relationships. They allow you to create new types based on the conditions of other types.

For example, you can use a conditional type to extract the return type of a function:

```typescript
type ReturnType<T> = T extends (…args: any[]) => infer R ? R : any;
type R1 = ReturnType<() => string>; // string
type R2 = ReturnType<() => void>; // void
```

You can also use conditional types to extract the properties of an object type that meet a certain condition:

```typescript
type PickProperties<T, U> = { [K in keyof T]: T[K] extends U ? K : never }[keyof T];
type P1 = PickProperties<{ a: number, b: string, c: boolean }, string | number>; // "a" | "b"
```

## Best Practice 19: Using Mapped Types

Mapped types are a way to create new types based on existing types. They allow you to create new types by applying a set of operations to the properties of an existing type.
For example, you can use a mapped type to create a new type that represents the readonly version of an existing type:

```typescript
type Readonly<T> = { readonly [P in keyof T]: T[P] };
let obj: { a: number, b: string } = { a: 1, b: "hello" };
let readonlyObj: Readonly<typeof obj> = { a: 1, b: "hello" };
```

You can also use a mapped type to create a new type that represents the optional version of an existing type:

```typescript
type Optional<T> = { [P in keyof T]?: T[P] };
let obj: { a: number, b: string } = { a: 1, b: "hello" };
let optionalObj: Optional<typeof obj> = { a: 1 };
```

Mapped types can be used in different ways: to create new types, to add or remove properties from an existing type, or to change the type of the properties of an existing type.

## Best Practice 20: Using Decorators

Decorators are a way to add additional functionality to a class, method or property using a simple syntax. They are a way to enhance the behavior of a class without modifying its implementation.

For example, you can use a decorator to add logging to a method:

```typescript
function logMethod(target: any, propertyKey: string, descriptor: PropertyDescriptor) {
 let originalMethod = descriptor.value;

 descriptor.value = function(…args: any[]) {
 console.log(`Calling ${propertyKey} with args: ${JSON.stringify(args)}`);
 let result = originalMethod.apply(this, args);
 console.log(`Called ${propertyKey}, result: ${result}`);
 return result;
 }
}

class Calculator {
 @logMethod
 add(x: number, y: number): number {
 return x + y;
 }
}
```

You can also use decorators to add metadata to a class, method or property, which can be used at runtime.

```typescript
function setApiPath(path: string) {
 return function (target: any) {
 target.prototype.apiPath = path;
 }
}

@setApiPath("/users")
class UserService {
 // …
}
console.log(new UserService().apiPath); // "/users"
```
