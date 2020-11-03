#### Hoisting

------

In JavaScript, all variable and function declarations are moved or *hoisted* to the top of their current scope, regardless of where it is defined. This is the default behavior of JavaScript interpreter which is called *hoisting*. 

> Case-1
>
> ```
> str = "Hello World!";
> alert(str); // Outputs: Hello World!
> var str;
> ```
>
> ```
> alert(str); // Outputs: undefined
> var str;
> str = "Hello World!";
> ```
>
> ```
> greet();
> function greet(){
> console.log("Hi! Bijay") // Outputs:Hi! Bijay
> }
> ```
>
> ```
> greet(); 
> var greet = function(){
> console.log("Hi! Bijay") // Outputs:Hi! Bijay
> }
> ....................Here greet variable is declared and hoisted but the greet is undefined but not supposed to greet() i.e function.
> ```

> Case-2
>
> ```
> printInfo();
> function printInfo(){
> console.log(myName);// Outputs:undefined
> var myName = "Bijay";
> }
> ```

> Case-3
>
> ```
> console.log(myName);
> let myName = "Bijay"; //Output:Unintialized but hoisted 
> ```
>
> ```
> let myName;
> console.log(myName);//Output:undefined
> ```

###### Special Cases:

```
var username = "Bijay";
function username(){
console.log("My name is Bijay");
}
console.log(username);//Output:"Bijay"
.......................It is because the variable assignmnet beats the function declaration.
```

```
var username;
function username(){
console.log("My name is Bijay");
}
console.log(username);//Output:"My name is Bijay"
.......................It is because the variable declaration not win over the function declaration.

```

