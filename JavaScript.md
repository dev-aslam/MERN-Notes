### JavaScript

### **<span style="color:blue">Scoping</span>**

Scope in JavaScript refers to the context or environment in which variables are declared and can be accessed. It dictates the visibility and lifetime of a variable, determining where in your code a particular variable is valid and accessible. JavaScript has 3 primary Scopes.

- **Global Scope**: Global scope is the widest scope available. Variables declared in global scope are accessible from anywhere in your code, whether it's inside functions, conditional statements, loops, or other blocks of code.

- **Local Scope**: When you declare a variable in local scope, it is limited in visibility to the block of code, function, or conditional statement in which it is defined. Variables in local scope are protected from interference or modification by code outside their scope, providing a level of isolation. Variables in local scope are typically declared within functions, conditional statements, loops, or other code blocks.

- **Block Scope**: Block scope in JavaScript is like a series of nested boxes within a larger container, each with its own set of variables. Unlike global and local scopes, which are defined by functions or global context, block scope is created within specific code blocks, such as conditional statements (if, else, switch) and loops (for, while). Variables declared in block scope are confined to that block, offering a high degree of isolation.

### **<span style="color:blue">Variable Shadowing</span>**

Variable shadowing occurs when you declare a variable with the same name inside a local scope, effectively "hiding" the variable with the same name in a higher scope.

### **<span style="color:blue">Closure and Function Scope</span>**

Think of closures as little "bundles" of code that encapsulate both a function and the variables it needs to work with. These bundles are like self-contained units of functionality that can be stored, passed around, and executed independently. In JavaScript, a closure is formed when a function is declared within another function, and the inner function has access to the variables of the outer function. This behavior is a result of function scope and the scope chain.

```javascript
function outerFunction() {
  var outerVariable = "I'm in outerFunction";
  function innerFunction() {
    console.log(outerVariable); // Accesses outerVariable from the outer scope
  }
  return innerFunction;
}
var closure = outerFunction();
closure(); // This still has access to outerVariable
```

In this code, innerFunction is declared inside outerFunction, forming a closure.
When outerFunction is called and assigned to the closure variable, it retains access to outerVariable even after outerFunction has completed.
This is the essence of a closure: the inner function remembers the scope in which it was created and can access its variables even when the outer function has finished executing.
<br><br>
**To read more on scope and closure refere [here](https://www.freecodecamp.org/news/scope-in-javascript-global-vs-local-vs-block-scope/)**

### **<span style ="color:blue">ECMA Script</span>**

ECMAScript (ES) is a standard for scripting languages, including JavaScript, JScript, and ActionScript. It is best known as a JavaScript standard intended to ensure the Compatibility of web pages across different web browsers.

### **<span style ="color:blue">JSON</span>**

JSON, or JavaScript Object Notation, is a way to store and exchange data in a simple and organized format. It's similar to how we write data in JavaScript objects, with keys and values.

**JSON Values**
In JSON, values must be one of the following data types:

- a string
- a number
- an object
- an array
- a boolean
- null

eg:

```javascript
{
  "name": "John Doe",
  "age": 30,
  "isEmployed": true,
  "hobbies": ["reading", "playing guitar", "hiking"]
}
```

JSON is popular because it's easy for both people and computers to understand. It's often used to send and receive data between different systems, like web servers and web browsers, because it's lightweight and flexible.

### **<span style ="color:blue">JSON.stringfy() and JSON.parse()</span>**

- **JSON.parse() :**
  <br>
  JavaScript has a built in function for converting JSON strings into JavaScript objects.
  <br>
- **JSON.stringify() :**
  <br>
  JavaScript also has a built in function for converting an object into a JSON string

### **<span style ="color:blue">Dynamic Typing</span>**

In dynamically-typed languages like JavaScript, the type of a variable is determined by the value it holds when the program is running. So, you don't need to specify the type of a variable explicitly; it can change as the program runs.

### **<span style ="color:blue">Hoisting</span>**

Hoisting in JavaScript is a behavior where variable and function declarations are moved to the top of their containing scope during the compile phase, before the code is executed.
In simpler terms, even if you declare a variable or function later in your code, JavaScript will process those declarations first, making them accessible throughout the entire scope.
eg:

```javascript
console.log(x); // undefined
var x = 5;
console.log(x); // 5
```

In the above code, even though x is logged before it's declared and assigned a value, JavaScript doesn't throw an error. Instead, it hoists the declaration of x to the top of the scope, resulting in undefined being printed first.<br>
However, it's important to note that only the declarations are hoisted, not the initializations. So, in the above example, var x is hoisted, but the assignment x = 5 remains in its original position

In JavaScript, there are primarily two types of hoisting: variable hoisting and function hoisting.

- **Variable Hoisting:**<br>
  variable hoisting refers to the behavior where variable declarations are moved to the top of their containing scope during the compile phase. There are mainly two types of variable hoisting:

  - **Var Hoisting:**<br>
    In JavaScript, variables declared with the var keyword are hoisted to the top of their function or global scope.
    When a variable is hoisted, it is initialized with a value of undefined.

    Eg:

    ```javascript
    console.log(x); // undefined
    var x = 5;
    console.log(x); // 5
    ```

    In this example, even though x is logged before it's declared and assigned a value, JavaScript hoists the declaration of x, resulting in undefined being printed first.4

  - **Let and Const Hoisting:**<br>
    Variables declared with let and const are hoisted to the top of their block scope, but unlike var, they are not initialized with a value.
    Accessing a let or const variable before its declaration (i.e., in the temporal dead zone) results in a ReferenceError.
    Eg:

    ```javascript
    console.log(x); // ReferenceError: Cannot access 'x' before initialization
    let x = 5;
    console.log(x);
    ```

    In this example, trying to access x before its declaration results in a ReferenceError.

### **<span style ="color:blue">Temporal Dead Zone (TDZ)</span>**

In JavaScript, the Temporal Dead Zone (TDZ) refers to the period between the start of a scope (such as a block or a function) and the actual declaration of a variable with `let` or `const`. During this time, accessing the variable results in a `ReferenceError`.<br>
Variables declared with `let` and `const` are hoisted to the top of their block scope, but they are not initialized until their actual declaration is reached in the code. Any attempt to access such variables before their declaration will throw a `ReferenceError`.

Eg:

```javascript
console.log(x); // ReferenceError: Cannot access 'x' before initialization
let x = 5;
console.log(x); // 5
```

In this example, trying to access x before its declaration results in a `ReferenceError` because it's still in the TDZ.

### **<span style ="color:blue">Null VS Undefinied</span>**

In JavaScript, `null` and `undefined` are both values used to represent the absence of a meaningful value, but they are used in slightly different contexts.

**`undefined`**

- `undefined` is a primitive value that is automatically assigned to variables that have been declared but not initialized.
- It indicates the absence of a value or the absence of a property in an object.

```javascript
let x;
console.log(x); // undefined

let obj = {};
console.log(obj.property); // undefined
```

**`null`**

- null is also a primitive value in JavaScript, but it is explicitly assigned to variables to indicate the absence of a value or to reset a variable.
- It is often used to represent intentional absence or the result of a deliberate action.

```javascript
let y = null;
console.log(y); // null
```

**When to Use Each**

- Use undefined when a variable has not been assigned a value or when accessing a property that does not exist.
- Use null when you want to explicitly indicate that a variable has no value or to reset a variable to indicate absence.

### **<span style ="color:blue">Void</span>**

- The void operator in JavaScript is primarily used to evaluate expressions or execute statements while ensuring that the result is discarded and always returns undefined.
- It's commonly used in scenarios involving JavaScript event handlers or anchor tags where you want to prevent the default behavior without affecting the current application state.

### **<span style ="color:blue">Set VS Array</span>**

**Set**

Sets are used to store collections of unique value without allowing duplication. The set is similar to the array and supports both insertion and deletion methods of the array. Sets are faster than arrays in terms of searching as they use a hash table internally for storing data and can be used to replace duplicates from other data types.

eg:

```javascript
let sample = new Set();
sample.add("Hello");
sample.add(1);
sample.add("Bye");
sample.add("@");
for (let item of sample) {
  console.log(item);
}
```

**Array**

The array is a data structure that is used to store data in a sequential manner of the same type. Arrays allow duplication of data and data is indexed which means that the data can be accessed according to its unique index.

```javascript
let sample = new Array();
sample.push("Hello");
sample.push("1");
sample.push("Bye");
sample.push("@");
console.log(sample);
console.log(sample[3]);
```

### **<span style ="color:blue">Pass by Value and Pass by Reference</span>**

**Pass By Value**

- In Pass by value, the function is called by directly passing the value of the variable as an argument. So any changes made inside the function do not affect the original value.
- In Pass by value, parameters passed as arguments create their own copy. So any changes made inside the function are made to the copied value not to the original value

eg:

```javascript
function Passbyvalue(a, b) {
  let tmp;
  tmp = b;
  b = a;
  a = tmp;
  console.log(`Inside Pass by value 
		function -> a = ${a} b = ${b}`);
}

let a = 1;
let b = 2;
console.log(`Before calling Pass by value 
		Function -> a = ${a} b = ${b}`);

Passbyvalue(a, b);

console.log(`After calling Pass by value 
	Function -> a =${a} b = ${b}`);

/*output
  Before calling Pass by value 
        Function -> a = 1 b = 2
Inside Pass by value 
        function -> a = 2 b = 1
After calling Pass by value 
       Function -> a =1 b = 2
*/
```

**Pass by Reference**

- In Pass by Reference, Function is called by directly passing the reference/address of the variable as an argument. So changing the value inside the function also change the original value. In JavaScript array and Object follows pass by reference property.
- In Pass by reference, parameters passed as an arguments does not create its own copy, it refers to the original value so changes made inside function affect the original value.

eg:

```javascript
function PassbyReference(obj) {
  let tmp = obj.a;
  obj.a = obj.b;
  obj.b = tmp;

  console.log(`Inside Pass By Reference 
		Function -> a = ${obj.a} b = ${obj.b}`);
}

let obj = {
  a: 10,
  b: 20,
};
console.log(`Before calling Pass By Reference 
	Function -> a = ${obj.a} b = ${obj.b}`);

PassbyReference(obj);

console.log(`After calling Pass By Reference 
	Function -> a = ${obj.a} b = ${obj.b}`);

/*output
Before calling Pass By Reference 
    Function -> a = 10 b = 20
Inside Pass By Reference 
        Function -> a = 20 b = 10
After calling Pass By Reference 
    Function -> a = 20 b = 10

*/
```

**To read more about pass by value and pass by reference check [geekforgeeks](https://www.geeksforgeeks.org/pass-by-value-and-pass-by-reference-in-javascript/)**

### **<span style ="color:blue">Shallow Copy and Deep Copy</span>**

In JavaScript, there are two ways to copy objects: Shallow copy and Deep copy

**Shallow Copy**

A shallow copy is a copy that only goes one level deep. In other words, it copies the object and all its properties, but any nested objects or arrays will still reference the same memory location as the original object. It means that if you make changes to the nested object, it will also affect the original object, as well as the copied object.

eg:

```javascript
const originalObject = { a: 1, b: { c: 2 } };
const shallowCopy = { ...originalObject };
```

In this example, originalObject has a nested object b that has a property c. The spread operator ... is used to create a new object shallowCopy. If we change the value of property a on shallowCopy does not affect originalObject. But changing the value of the property c on the nested object b affects both shallowCopy and originalObject.

It is because shallowCopy and originalObject both have a reference to the same nested object b. When we modify b on shallowCopy, it modifies the same object on originalObject.

**Deep Copy**

A deep copy is a copy that creates a new object with new memory locations for all of its properties and nested objects or arrays. It means that if you make changes to the copied object or any of its nested objects or arrays, it will not affect the original object.

eg:

```javascript
const originalObject = { a: 1, b: { c: 2 } };
const deepCopy = JSON.parse(JSON.stringify(originalObject));
```

In this example, we use JSON.stringify() to convert originalObject to a JSON string, and then use JSON.parse() to convert that string back to a new object deepCopy. It creates a deep copy of originalObject.

Changing the value of the property a or the nested object b on deepCopy does not affect originalObject. It is because deepCopy and originalObject have separate memory locations for all of their properties and nested objects

### **<span style ="color:blue">Prototype</span>**

In JavaScript, every object has a special hidden property called a prototype. This prototype is simply a reference to another object and contains shared attributes or methods that all instances of the object can use.

- Prototypes in JavaScript allow objects to share common properties and methods.
- Every object has a prototype, which it inherits properties and methods from.
- Constructor functions are used to create objects with predefined behavior, and newly created objects automatically inherit properties and methods from the constructor's prototype.

Example:<br>
For example, every array in JavaScript has a prototype object called Array.prototype. This prototype object contains common methods like `sort()`, `map(),` and `filter()` that can be used by all arrays.
<br>
Similarly, objects like `Date`, `String`, and `Function` also have their own prototype objects with shared methods.

**How Prototypes Work:**<br>
When you create a new object, it automatically inherits properties and methods from its prototype. This means that you can use methods like `sort()` on an array instance because it inherits that method from `Array.prototype.`

**Constructor Functions:**<br>
Constructor functions are special functions used to create objects with a specific structure and behavior. When you create an object using a constructor function and the `new` keyword, the newly created object automatically inherits properties and methods from the constructor's prototype.

eg:

```javascript
function Car(make, model) {
  this.make = make;
  this.model = model;
}

Car.prototype.getColor = function () {
  return this.color;
};

const firstCar = new Car("Toyota", "Camry");
```

In this example, the `Car` function acts as a constructor for creating car objects. The `getColor` method is added to the `Car.prototype`, so all instances of `Car` objects, like `firstCar`, can use this method

### **<span style ="color:blue">Prototype chain</span>**

In JavaScript, when you try to access a property on an object and that property doesn't exist on the object itself, JavaScript looks for it in the object's prototype. If it's not found there, it keeps searching up the prototype chain until it finds the property or reaches the end of the chain.

**The Great Ancestral Prototype**<br>
At the top of this prototype chain is a special object called Object.prototype. This is like the great ancestor of all objects in JavaScript. It provides default properties and methods that are shared by almost all objects.
<br>
While `Object.prototype` is the ultimate ancestor, not all objects directly inherit from it. Many objects have a different object as their prototype, which provides a different set of default properties and methods.

**To read in details about prototype check [here](https://medium.com/backticks-tildes/javascript-prototypes-ee46810e4866)**

### **<span style ="color:blue">Currying </span>**

Currying is a concept in functional programming that allows you to transform a function with multiple arguments into a sequence of functions, each taking only one argument at a time. This technique enhances code reusability, composability, and maintainability by breaking down complex functions into simpler, reusable ones.

**How Currying Works**<br>
When you curry a function, you convert it into a series of nested functions, with each function taking one argument. These nested functions are called one after the other, each returning a new function until all arguments are provided. Once all arguments are supplied, the original function is executed with those arguments.

eg:

```javascript
// Non-curried function
function add(a, b, c) {
  return a + b + c;
}

// Curried version
function curriedAdd(a) {
  return function (b) {
    return function (c) {
      return a + b + c;
    };
  };
}

// Usage of curried function
const result = curriedAdd(1)(2)(3); // Result: 6
```

In this example, `curriedAdd` is a curried version of the `add` function. Each call to `curriedAdd` returns a new function that expects the next argument. Finally, when all arguments are provided, the original `add` function is executed.

**Benefits of Currying**

- **Code Reusability:** Curried functions can be reused with different arguments, promoting code reuse.
- **Composability:** Curried functions can be easily composed together to create new functions, enhancing code modularity.
- **Partial Application:** Currying allows for partial application of arguments, making functions more flexible and adaptable to different scenarios.
  Methods of Currying

**Refer [here](https://designtechworld.medium.com/everything-about-currying-in-javascript-a2614b82e6ca) to learn more about currying**

### JavaScript Resources to refer

1. [Namaste JavaScript](https://www.youtube.com/playlist?list=PLxnjbfm5MCHFbRlyVCAqpJFdIzPN_IPID)

2. [MDN Web Docs](https://developer.mozilla.org/en-US/docs/Web/JavaScript)

3. [JavaScript Roadmap](https://roadmap.sh/javascript)

4. [Yestech Media](https://www.youtube.com/watch?v=8BWQdKBh2Aw&list=PL1JrLEBAapUVNy5sRQVtQgs7ep6mZZ-YG)
