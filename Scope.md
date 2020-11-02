#### Scope ::mag:

Scope determines the accessibility (visibility) of variables.

------

##### 1. Global Scope 

If a variable is declared outside all functions or curly braces (`{}`), it is said to be defined in the **Global Scope**. Once you’ve declared a global variable, you can use that variable anywhere in your code, even in functions.



> ##### When you define a `var` in the global scope it’s publicly available in the global object. But When you define a `let` or `const` variable, it’s publicly available but not bound to the global object.



```
var hello = 'Hello Bijay'

function sayHello () {
  console.log(hello)
}

console.log(hello) // 'Hello Bijay!'
sayHello() // 'Hello Bijay!'
```



##### 2. Local Scope

Variables that are usable only in a specific part of your code are considered to be in a local scope. These variables are also called **local variables**.

In JavaScript, there are two kinds of local scope: function scope and block scope.



###### i. <u>Function scope</u>

When you declare a variable in a function, you can access this variable only within the function. You can’t get this variable once you get out of it.



> Parameter passes through the function are also function scoped



```
function sayHello () {
  const hello = 'Hello CSS-Tricks Reader!'
  console.log(hello)
}

sayHello() // 'Hello CSS-Tricks Reader!'
console.log(hello) // Error, hello is not defined.
```



###### ii. <u>Block Scope</u>

When you declare a variable with `const` or `let` within a curly brace (`{}`), you can access this variable only within that curly brace.

```
{
  const hello = 'Hello CSS-Tricks Reader!'
  console.log(hello) // 'Hello CSS-Tricks Reader!'
}

console.log(hello) // Error, hello is not defined
```

##### Special Cases:

For try{...}catch(err){...},parameter "err" is only available inside the catch block only.

##### Variable Shadowing

Variable Shadowing occurs when a variable is declared in certain scope has the same name defined on it’s outer scope. And when we call the variable from the inner scope, the value mentioned in inner scope will be taken into account.

```
var a = 10;
console.log(a);// a = 10;
function VariableShadowing() {
var a = 20;
console.log(a);// a = 20;
}
VariableShadowing();
```

