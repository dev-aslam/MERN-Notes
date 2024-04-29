### JavaScript Pending Topics

**Scoping**
Scope in JavaScript refers to the context or environment in which variables are declared and can be accessed.It dictates the visibility and lifetime of a variable, determining where in your code a particular variable is valid and accessible.
JavaScript have 3 primary Scopes.

- global, local, and block scope.

**Global Scope**
global scope is the widest scope available. Variables declared in global scope are accessible from anywhere in your code, whether it's inside functions, conditional statements, loops, or other blocks of code.

**Local Scope**
When you declare a variable in local scope, it is limited in visibility to the block of code, function, or conditional statement in which it is defined.
Variables in local scope are protected from interference or modification by code outside their scope, providing a level of isolation.
Variables in local scope are typically declared within functions, conditional statements, loops, or other code blocks.

**Block Scope**
Block scope in JavaScript is like a series of nested boxes within a larger container, each with its own set of variables.
Unlike global and local scopes, which are defined by functions or global context, block scope is created within specific code blocks, such as conditional statements (if, else, switch) and loops (for, while).
Variables declared in block scope are confined to that block, offering a high degree of isolation.

**Variable Shadowing**
Variable shadowing occurs when you declare a variable with the same name inside a local scope, effectively "hiding" the variable with the same name in a higher scope.

**Closure and Function Scope**
Think of closures as little "bundles" of code that encapsulate both a function and the variables it needs to work with.
These bundles are like self-contained units of functionality that can be stored, passed around, and executed independently.
In JavaScript, a closure is formed when a function is declared within another function, and the inner function has access to the variables of the outer function.
This behavior is a result of function scope and the scope chain.

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

**To read more on scope and closure refere [here](https://www.freecodecamp.org/news/scope-in-javascript-global-vs-local-vs-block-scope/)**

### JavaScript Resources to refer

1. [Namaste JavaScript](https://www.youtube.com/playlist?list=PLxnjbfm5MCHFbRlyVCAqpJFdIzPN_IPID)

2. [MDN Web Docs](https://developer.mozilla.org/en-US/docs/Web/JavaScript)

3. [JavaScript Roadmap](https://roadmap.sh/javascript)

4. [Yestech Media](https://www.youtube.com/watch?v=8BWQdKBh2Aw&list=PL1JrLEBAapUVNy5sRQVtQgs7ep6mZZ-YG)
