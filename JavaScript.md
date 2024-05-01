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

### **<span style ="color:blue">Web API </span>**

Web APIs is an application programming interface that provides additional functionality to the web browser or the web server. It allows JavaScript code to access data or perform tasks that are not part of the core JavaScript language, such as manipulating the document object model (DOM), sending HTTP requests, playing audio or video, using geolocation, etc.

Web APIs is not part of the basic JavaScript language, but it works with it. It uses some other code that can talk to the web browser or the web server. Web APIs can be of two types: browser APIs and third-party APIs.

**Browser APIs**<br>
Browser APIs are built into the web browser and are available to all web pages and applications. They expose data from the browser and the surrounding computer environment, such as `window`, `document`, `navigator`, `localStorage`, etc. They also provide methods to manipulate or use this data, such as `setTimeout()`, `alert()`, `fetch()`, etc.

**Third-party APIs**<br>
Third Party APIs are not built into the web browser by default, but they can be retrieved from somewhere on the web. They usually require some authentication or authorization to access their services or data. For example, the `Twitter APIs` allow you to display your latest tweets on your website. It provides a special set of constructs you can use to query the Twitter service and return specific information.

**Categories of browser APIs**

- **XMLHttpRequest (XHR) API:**<br>
  The XHR API allows web browsers to make HTTP requests to fetch data from servers asynchronously. It enables the implementation of AJAX (Asynchronous JavaScript and XML) to create dynamic web pages that can fetch and display data without requiring a page reload.

- **Fetch API:**<br>
  These are capable of making HTTP requests to a web server. The response can be in JSON, plain text, or XML format. The fetch API is a modern replacement for XHR. It was introduced in browsers recently to make asynchronous HTTP requests easier.

- **APIs for manipulating document structure (DOM)**<br>
  The DOM API provides a structured representation of HTML and XML documents, allowing JavaScript to manipulate their content, structure, and style dynamically. This allows you to manipulate HTML and CSS in creating, removing, and also dynamically applying new styles to your page.

- **Storage APIs:**<br>
  These APIs give the ability to store data on the client-side, which is very useful for storing certain user data for some time. One of which is the Web Storage API. These can either be the sessionStorage, which keeps data for the duration of the session, or the localStorage, which retains the data even after the browser is closed
  - **Web Storage API**:
    The Web Storage API allows web applications to store key-value pairs locally on the client-side browser, providing a way to persist data across page reloads and browser sessions. It includes mechanisms such as localStorage and sessionStorage.
- **APIs for drawing graphics:**<br>
  Modern web browsers today now support the creation of graphics on the web. One of the APIs is the Canvas API. It provides a means for drawing graphics using JavaScript and HTML. Different shapes, objects, and styles can be created using this API.
  It enables web developers to programmatically interact with and modify web page elements.
  - **Canva API:**
    The Canvas API allows dynamic rendering of graphics and images on web pages using JavaScript. It provides a drawing context for creating and manipulating bitmap images and graphics directly within the browser.
  - **WebGL API:**
    WebGL is a JavaScript API for rendering interactive 2D and 3D graphics within compatible web browsers. It provides access to the GPU (Graphics Processing Unit) for high-performance graphics rendering.
- **Audio and Video APIs:**<br>
  These APIs can manage, display, and create different media types. Some of which are:

  - **Web Audio API:**
    The Web Audio API provides a platform for controlling audio and allowing developers to choose audio sources, add effects to audio, create audio visualizations, apply spatial effects (such as panning) and much more.
  - **The WebRTC (Web Real-Time Communication) API:**
    It makes it possible to stream live audio and video, as well as transfer arbitrary data between two peers over the internet without requiring an intermediary.

**To learn more about different type of Web APIs, refer [here](https://developer.mozilla.org/en-US/docs/Web/API)**

**[MDN Docs on Client-side web APIs](https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Client-side_web_APIs)**

### **<span style ="color:blue">JavaScript Runtime and Web APIs Interaction </span>**

When a JavaScript program runs in the browser, it interacts with various parts of the browser environment, such as the DOM (Document Object Model), timers, network requests, and more.

1. **Call Stack:**<br>
   The call stack is a fundamental part of the JavaScript runtime. It keeps track of the execution context of functions. When a function is invoked, a new frame representing that function is pushed onto the call stack. When the function finishes executing, its frame is popped off the stack.
2. **Web APIs Stack:**<br>
   Web APIs are provided by the browser environment and include features like `setTimeout`, `fetch`, and `XMLHttpRequest`. When you call an asynchronous function like setTimeout, it's handed off to the browser's Web APIs for execution. These functions are executed independently of the main JavaScript thread, allowing the rest of your code to continue running.
3. **Callback Queue:**<br>
   Asynchronous functions, when completed, don't immediately return their results to the JavaScript code. Instead, they place their callback functions (or events) in a queue known as the callback queue. This queue holds functions that are ready to be executed once the call stack is empty and the event loop can retrieve them.
4. **Event Loop:**<br>
   The event loop ensures JavaScript code and Web APIs work harmoniously together. It continuously monitors the call stack and the callback queue. If the call stack is empty and there are functions waiting in the callback queue, the event loop moves those functions from the queue to the call stack for execution.

eg:

```javascript
console.log("Start");

setTimeout(function () {
  console.log("Inside setTimeout");
}, 2000);

console.log("End");
```

- In this example, `"Start"` and `"End"` are added to the call stack and executed synchronously.
- When setTimeout is encountered, it's passed to the Web APIs stack for a timer to be set. After 2 seconds, the callback function is placed in the callback queue.
- Meanwhile, `"End"` is logged to the console.
- Once the call stack is empty, the event loop moves the callback function from the callback queue to the call stack, where it's executed, resulting in "Inside setTimeout" being logged to the console.

![JS Runtime](https://miro.medium.com/v2/resize:fit:720/format:webp/1*DhFeUdVpRbEq76ddF86sKg.jpeg)

### **<span style ="color:blue">Higher Order Function</span>**

A higher order function is a function that takes one or more functions as arguments, or returns a function as its result.<br>
There are several different types of higher order functions like map and reduce.

eg:

```javascript
// Callback function, passed as a parameter in the higher order function
function callbackFunction() {
  console.log("I am  a callback function");
}

// higher order function
function higherOrderFunction(func) {
  console.log("I am higher order function");
  func();
}

higherOrderFunction(callbackFunction);
```

In the above code higherOrderFunction() is an HOF because we are passing a callback function as a parameter to it.

### **<span style ="color:blue">Promise</span>**

The Promise object represents the eventual completion (or failure) of an asynchronous operation and its resulting value.<br>
A Promise is a JavaScript object used for managing asynchronous operations.<br>
Promises allow you to write code that continues after a specific event occurs without blocking the execution of other code; JavaScript continues to read the code asynchronously.<br>
Promises enable the handling of data that is not currently available but will be available in the future.

A Promise has three states:

- **Pending:** This is the initial state when the Promise is neither fulfilled nor rejected. It represents the state of the Promise while the asynchronous operation is still ongoing.
- **Fulfilled:** This state signifies that the asynchronous operation associated with the Promise has been successfully completed.
- **Rejected:** This state indicates that the asynchronous operation has failed or been rejected for some reason.

Promises transition from the “Pending” state to either “Fulfilled” or “Rejected” once the asynchronous operation is completed. These states help manage the flow of asynchronous code and handle its outcomes.

When a Promise is either fulfilled or rejected, it enters the `settled` state, and in this step, there are two important methods:

- **then:** When a Promise successfully transitions to the `fulfilled` state, the `then` method allows you to specify a callback function or code block that will work with the completed data. This is used to define what should happen when a successful result is obtained.

- **catch:** When a Promise transitions to the “rejected” state, the catch method lets you specify a callback function or code block that will work with the rejected error. This is used to handle situations where the operation fails.

eg:

```javascript
const myPromise = new Promise((resolve, reject) => {
  setTimeout(() => {
    const randomNumber = Math.random();
    if (randomNumber < 0.5) {
      resolve("Data has been successfully retrieved.");
    } else {
      reject("An error occurred while fetching data.");
    }
  }, 1000);
});

myPromise
  .then((data) => {
    console.log(data);
  })
  .catch((error) => {
    console.error(error);
  });
```

In the above example We’ve added logic to randomly either resolve the Promise with a success message or reject it with an error message.
We use the then method to handle the successful resolution and print the success message.
We use the catch method to handle any errors and print the error message if the Promise is rejected.

### **<span style ="color:blue">Promise Chaining</span>**

Promise chaining is a concept in JavaScript used to handle asynchronous operations in a sequential manner.Promise chaining allows you to execute multiple asynchronous operations one after the other, ensuring that each operation completes before the next one begins.

```javascript
fetchData()
  .then((data) => {
    return otherFetchData(data);
  })
  .then((chainData) => {
    return chainData.response;
  })
  .catch((error) => {
    console.log(error);
  });
```

- A Promise chain is created by adding multiple `.then()` methods.
- The initial Promise starts the chain, and each function within a `.then()` becomes a Promise itself, and their return values are passed to the next link in the chain.
- Only one `.catch()` is sufficient within the Promise chain. If an unexpected error occurs within the chain, the subsequent `.then()` links are skipped, and the function inside `.catch()` is executed.

### **finally()**

The .finally() method is another feature of promises in JavaScript, It allows you to specify a function that will be executed regardless of whether the promise is resolved or rejected. This is useful for performing cleanup operations or tasks that need to be executed regardless of the outcome of the promise.

eg:

```javascript
asyncTask()
  .then((result) => {
    console.log(result);
  })
  .catch((error) => {
    console.error(error);
  })
  .finally(() => {
    console.log("Cleanup code here");
  });
```

- If the promise returned by asyncTask() is resolved, the .then() block will execute, logging the result.
- If the promise is rejected, the .catch() block will execute, logging the error.
- Regardless of whether the promise is resolved or rejected, the .finally() block will execute, allowing you to perform cleanup operations such as closing files, releasing resources, or logging.

### **<span style ="color:blue">Promise Combinators or Promise Concurrency</span>**

Promise combinators are higher-order functions that allow you to combine multiple promises to perform operations on them collectively.Each combinator method takes in an array of promises as an argument.Each combinator method in-turn returns a Promise.

**Promise.all() method:**

The `Promise.all()` method takes an array of promises and returns a single promise that resolves when all of the promises in the collection have resolved, or rejects with the reason of the first promise that rejects. It's useful when you want to perform multiple asynchronous operations concurrently and wait for all of them to complete before proceeding.

`Fulfills when all of the promises fulfill; rejects when any of the promises rejects.`
<br>
eg:

```javascript
const p1 = Promise.resolve(3);
const p2 = 1337;
const p3 = new Promise((resolve, reject) => {
  setTimeout(() => {
    resolve("foo");
  }, 100);
});

Promise.all([p1, p2, p3]).then((values) => {
  console.log(values); // [3, 1337, "foo"]
});
```

**Promise.race() method:**

`Promise.race()` is a method that takes a collection of promises and returns a new promise. This new promise resolves or rejects as soon as one of the promises in the collection settles (resolves or rejects), taking on the value or reason of that promise. It's particularly handy when you're interested in the outcome of the first promise that completes among several asynchronous operations.

`Settles when any of the promises settles. In other words, fulfills when any of the promises fulfills; rejects when any of the promises rejects.`

eg:

```javascript
const promise1 = new Promise((resolve, reject) => {
  setTimeout(resolve, 500, "one");
});

const promise2 = new Promise((resolve, reject) => {
  setTimeout(resolve, 100, "two");
});

Promise.race([promise1, promise2]).then((value) => {
  console.log(value); // 'two' (because promise2 resolves first)
});
```

**Promise.allSettled():**

`Promise.allSettled()` is a method that takes a collection of promises and returns a new promise. This new promise resolves after all of the promises in the collection have settled (either resolved or rejected). It provides an array of objects, each describing the outcome of each promise, with information about whether it was fulfilled or rejected, and the value or reason accordingly. This method is particularly useful when you need to handle all promise outcomes, regardless of whether they resolve or reject.

`Fulfills when all promises settle.`

eg:

```javascript
const promise1 = Promise.resolve(42);
const promise2 = Promise.reject("Error occurred");
const promise3 = new Promise((resolve, reject) => {
  setTimeout(resolve, 1000, "Third promise resolved");
});

Promise.allSettled([promise1, promise2, promise3]).then((results) => {
  console.log(results);
});

/*output
[
  { status: 'fulfilled', value: 42 },              // Result of promise1
  { status: 'rejected', reason: 'Error occurred' }, // Result of promise2
  { status: 'fulfilled', value: 'Third promise resolved' } // Result of promise3
]
*/
```

**Promise.any():**

`The Promise.any()` function takes a collection of promises as input and returns a single promise. This returned promise resolves as soon as any promise in the collection resolves, providing the value of the first resolved promise. However, if all promises in the collection are rejected (or if the collection is empty), the returned promise is rejected with an AggregateError, which includes a list of reasons for each rejection.

`Fulfills when any of the promises fulfills; rejects when all of the promises reject.`

eg:

```javascript
const promise1 = new Promise((resolve, reject) => {
  setTimeout(reject, 1000, "First promise rejected");
});

const promise2 = new Promise((resolve, reject) => {
  setTimeout(resolve, 500, "Second promise resolved");
});

const promise3 = new Promise((resolve, reject) => {
  setTimeout(reject, 1500, "Third promise rejected");
});

Promise.any([promise1, promise2, promise3])
  .then((value) => {
    console.log(value); // 'Second promise resolved'
  })
  .catch((error) => {
    console.error(error); // AggregateError: All promises were rejected
  });
```

**Thenable**

A "thenable" is an object that has a `.then()` method. This method allows it to be used in promise chains, enabling interoperability with promises. While it may not necessarily be a full-fledged promise object, as long as it has a `.then()` method conforming to the Promises/A+ specification, it can be treated as a promise-like object.

**Read more about promise [mdn Docs](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise), [Medium](https://medium.com/insiderengineering/mastering-javascript-promises-from-basics-to-advanced-f24669381c56)**

### **<span style ="color:blue">Strict Mode</span>**

Strict mode is a feature in JavaScript that lets you write code in such a way that follows stricter rules. This means you may be able to catch some common errors that would have otherwise gone unnoticed. It also helps you write cleaner and more secure code.

To enable strict mode for the whole JavaScript file, you simply add the string `use strict` to the top of your code.

**Features Strict Mode**

- **Preventing Silent Errors**: In non-strict mode, some actions that would otherwise result in errors are silently ignored. Strict mode makes these errors explicit, helping you catch them early during development.

- **Avoiding Global Variables**: In strict mode, assigning a value to an undeclared variable results in a `ReferenceError`. This prevents accidental creation of global variables and encourages cleaner code.

- **Restricting `this` Binding**: In non-strict mode, `this` can refer to the global object when a function is called without an explicit context. Strict mode makes `this` `undefined` in such cases, preventing unintentional behavior.

- **Eliminating Octal Syntax**: In strict mode, octal syntax (e.g., `010`) is not allowed, preventing potential confusion and unexpected behavior.

- **Prohibiting `with` Statements**: In strict mode, the use of `with` statements is not allowed. This is because `with` can introduce ambiguity and make code harder to understand and optimize.

- **Using an Undeclared Variable**: In strict mode, all variables and objects must be declared before use. This prevents accidental creation of global variables, improving code quality and reducing bugs.

- **Duplicating a Parameter Name**: In non-strict mode, duplicating a parameter name in a function is allowed, with only the last instance of the duplicates being recognized. However, strict mode disallows parameter name duplication, throwing a syntax error to catch potential mistakes early.

- **Using Reserved Future Keywords**: JavaScript reserves certain keywords for potential future use, and using them as identifiers (such as variables or function names) might cause issues in future versions. Strict mode prevents the use of these reserved keywords as identifiers, ensuring compatibility with future JavaScript versions.

- **Use of Deprecated Features**: Strict mode restricts the use of deprecated JavaScript features like `arguments.caller` and `arguments.callee`, which are disallowed due to security and performance concerns. In contrast, non-strict mode allows the use of these deprecated features.

- **Assignment to a Read-Only Property**: In non-strict mode, attempting to assign a new value to a read-only property silently fails without throwing an error. However, strict mode functions do not allow this behavior and instead throw a syntax error to alert developers to the issue.

### **<span style ="color:blue">Class</span>**

In JavaScript, a class is a blueprint for creating objects with similar properties and methods. It provides a way to define the structure and behavior of objects. You can think of a class as a template or a prototype from which individual objects can be created. It encapsulates data for the object it creates and defines methods to operate on that data. JavaScript classes use a syntax similar to other object-oriented programming languages like Java or C++, making it easier to organize and manage code.

```javascript
class Person {
  // Constructor method
  constructor(name, age) {
    this.name = name;
    this.age = age;
  }

  // Instance method
  greet() {
    return `Hello, my name is ${this.name} and I'm ${this.age} years old.`;
  }
}

// Creating an instance of the Person class
const john = new Person("John", 30);

// Calling the greet() method on the instance
console.log(john.greet()); // Output: Hello, my name is John and I'm 30 years old.
```

### **<span style ="color:blue">Destructuring</span>**

Destructuring Assignment is a JavaScript expression that allows to unpack values from arrays, or properties from objects, into distinct variables data can be extracted from arrays, objects, nested objects and assigning to variables.

**Array desturcturing**

```javascript
const numbers = [1, 2, 3, 4, 5];

// Extracting values from array
const [first, second, ...rest] = numbers;

console.log(first); // Output: 1
console.log(second); // Output: 2
console.log(rest); // Output: [3, 4, 5]
```

**Object desturcturing**

```javascript
const person = {
  name: "John",
  age: 30,
  country: "USA",
};

// Extracting values from object
const { name, age, country } = person;

console.log(name); // Output: John
console.log(age); // Output: 30
console.log(country); // Output: USA
```

**Default Values and Renaming**

```javascript
const settings = {
  apiKey: "abc123",
  timeout: 5000,
};

// Destructuring with default values and renaming
const {
  apiKey: key = "defaultApiKey",
  timeout = 3000,
  secure = true,
} = settings;

console.log(key); // Output: abc123
console.log(timeout); // Output: 5000 (default value overridden by value in settings)
console.log(secure); // Output: true (default value used as it's not present in settings)
```

**Nested Destructuring**

```javascript
const user = {
  name: "Alice",
  age: 25,
  address: {
    city: "New York",
    country: "USA",
  },
};

// Nested destructuring
const {
  name,
  address: { city, country },
} = user;

console.log(name); // Output: Alice
console.log(city); // Output: New York
console.log(country); // Output: USA
```

### **<span style ="color:blue">Removing Object Key</span>**

To remove a key from an object in JavaScript, you can use the `delete` operator

eg:

```javascript
let obj = {
  key1: "value1",
  key2: "value2",
  key3: "value3",
};

delete obj.key2;

console.log(obj); // Output: { key1: 'value1', key3: 'value3' }
```

### **<span style ="color:blue">Javascript Scheduling: setTimeout and setInterval (Timer Functions)</span>**

**setTimeout(callback, delay)**

The `setTimeout()` function is commonly used if you wish to run your function a specified number of milliseconds from when the `setTimeout()` method was called. The general syntax of the method is:

`setTimeout ( expression, timeout );` <br>
where expression is the JavaScript code or callback function to run after timeout milliseconds have elapsed.

```javascript
setTimeout(() => {
  console.log("Delayed message");
}, 1000); // Execute after 1 second
```

**setInterval(callback, delay)**

The `setInterval()`Executes a function (`callback`) repeatedly at a specified interval (in milliseconds), until `clearInterval` is called - they even have same syntax:

`setInterval ( expression, interval );`

```javascript
setInterval(() => {
  console.log("Repeated message");
}, 2000); // Execute every 2 seconds
```

`setTimeout()` triggers the expression only once while `setInterval()` keeps triggering expressionregularly after the given interval of time.

**clearInterval(timeoutId)**

Cancels a timeout previously established by calling `setTimeout`.

```js
let timeoutId = setTimeout(() => {
  console.log("Delayed message");
}, 1000);

clearTimeout(timeoutId); // Cancel the timeout
```

**clearInterval(intervalId)**

Cancels a timer previously established by calling `setInterval`.

```js
let intervalId = setInterval(() => {
  console.log("Repeated message");
}, 2000);

clearInterval(intervalId); // Cancel the interval
```

### **<span style ="color:blue">Variadic Functions</span>**

In JavaScript, a variadic function is a function that can accept a variable number of arguments. This means the function can be called with any number of arguments, including none at all.

you can achieve variadic behavior using the `arguments` object or the rest parameter syntax `(...args)`.

**Arguments object**

The arguments object is available inside every function and allows you to access all arguments passed to the functions. Even arguments do not declare explicitly in function. An argument object is like an array of arguments of functions.

eg:

```js
function SumOfNum() {
  let total = 0;
  for (let i = 0; i < arguments.length; i++) {
    total += arguments[i];
  }
  return total;
}

console.log("Sum is ", SumOfNum(1, 2, 3, 4)); //10
console.log("Sum is ", SumOfNum(1, 2, 5)); //8
```

**Rest parameter**

The rest parameter allows you to collect a variable number of arguments into an array parameter. To achieve variadic functions behavior using rest parameter, you can define a single argument inside a function using the rest operator.

```js
function SumOfNum(...numbers) {
  let total = 0;
  for (let i = 0; i < numbers.length; i++) {
    total += numbers[i];
  }
  return total;
}

console.log("Sum is ", SumOfNum(1, 2, 3, 4));
console.log("Sum is ", SumOfNum(1, 2, 5));
```

## JavaScript Resources to refer

1. [Namaste JavaScript](https://www.youtube.com/playlist?list=PLxnjbfm5MCHFbRlyVCAqpJFdIzPN_IPID)

2. [MDN Web Docs](https://developer.mozilla.org/en-US/docs/Web/JavaScript)

3. [JavaScript Roadmap](https://roadmap.sh/javascript)

4. [Yestech Media](https://www.youtube.com/watch?v=8BWQdKBh2Aw&list=PL1JrLEBAapUVNy5sRQVtQgs7ep6mZZ-YG)
