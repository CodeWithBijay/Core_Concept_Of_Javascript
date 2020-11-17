JavaScript objects are containers for **named values** called properties or methods.

```javascript
var person = {
  firstName: "John",
  lastName: "Doe",
  age: 50,
  eyeColor: "blue"
};
const personReference = person;
personReference.firstName = "Bijay";
console.log(personReference)//💘💘
console.log(person === personReference);//True
console.log({} instanceof Object);//True
console.log(Object() instanceof Object);//True
```

## Accessing of Object Properties

```
objectName.propertyName
```

```
objectName["propertyName"]
```

## Object Methods

Objects can also have **methods**. Methods are **actions** that can be performed on objects. Methods are stored in properties as **function definitions**. A method is a function stored as a property.

```javascript
var person = {
  firstName: "John",
  lastName : "Doe",
  id       : 5566,
  fullName : function() { //🚫 Not to Use arrow Function
    return this.firstName + " " + this.lastName;
  }
};
```

## Creating Short-Hand Object key and properties:

##  

```javascript
 let firstName = "John";
  let lastName = "Doe";
  let id = 5566;
  let somekey = "firstName";
var person = {
  [somekey]:firstName,
  lastName,
  id,
  fullName : function() { //🚫 Not to Use arrow Function
    return this.firstName + " " + this.lastName;
  }
};
```

## Object De-structuring:

```javascript
//Ordinay way of doing
var person = {
  firstName: "John",
  lastName : "Doe",
  id       : {
  primary:123,
  secondary:321
  }
  }
  const myFirstName = person.firstName;
  const myLastName = person.lastName;
  const myIdPrimary = person.id.primary);
  console.log(myFirstName,myLastName,myIdPrimary);
```

```javascript
var person = {
  firstName: "John",
  lastName : "Doe",
  id : {
  primary:123,
  secondary:321
  }
  }
/*const {firstName,lastName,id} = person;
console.log(firstName,lastName,id);*/

    /*const {firstName :fn,lastName,id :{ primary }} = person;
console.log(fn,lastName,primary);*/
const {firstName :fn,id :{ primary }, ...rest} = person;
console.log(fn,primary,rest );
```

## Properties and Value Checking In Objects

```javascript
var person = {
  firstName: "John",
  lastName : "Doe",
  id       : {
  primary:123,
  secondary:321
  },
  /*hasOwnProperty(){
  return true;
}*/
  }
//Value Check  
if(person.firstName){
console.log(person.firstName);
}
for(const prop in person) {
if(person[prop] === "firstName"){
console.log(person[prop]);
}
}
const hasJohn = Object.values(person).includes("John");
console.log(hasJohn)
//Property Check
console.log(person.hasOwnProperty('lastName'));
console.log(Object.prototype.hasOwnProperty.call(person, "firstName"));//Bullet Proof👁️👁️
```

## Adding and Updating Object Values and Properties

```
var person = {
  firstName: "John",
  lastName : "Doe",
  id       : {
  primary:123,
  secondary:321
  }
  }
  //Odinary Way
  person.address = "Bankatta";
  person.name = "Himani";
  
  //Modern Way
  function propUpdate(prop, value) {
  person[prop] = value;
  }
  propUpdate("address","Bankatta");
  propUpdate("firstName","Himani")

```

## Removing Object Properties

```javascript
var person = {
  firstName: "John",
  lastName : "Doe",
  id       : {
  primary:123,
  secondary:321
  }
  }
  //slow
  //delete person.firstName;
  
  person.firstName = undefined;
  if(person.firstName){
  console.log("Has FirstName...");
  }
  console.log(person.hasOwnProperty('firstName'));
  const{ id,...rest } = person;
  console.log(id, rest, person);
```

## Shallow and Deep Clone

```
const drink = {
id:"6565shgs",
name : "Alcohol",
price : {
sale : 99,
full : 126,
},
}
//Shallow Copies
//const drinkClone = Object.assign({}, drink);
//const drinkClone = {...drink };
//Deep Copies
const drinkStringified = JSON.stringify(drink);
const drinkClone = JSON.parse(drinkStringified);
drinkClone.id = "ajak";
drinkClone.price.sale = 79;
console.log(drink);
```

## Merging Two Object:

```javascript
const drink = {
id:"6565shgs",
name : "Alcohol",
};
const price = {
sale : 99,
full : 126,
};
const mergedDrink = Object.assign({}, drink,{ price });
//const mergedDrink = {...drink, ...{price}};
console.log(drink,price,mergedDrink);
```

## Type Checking In Object:

```javascript
const drink = {
id:"6565shgs",
name : "Alcohol",
};
function getType(obj){
return Object.prototype.toString.call(obj);
}
console.log(typeof drink);
console.log(typeof []);
console.log(typeof null);
console.log({} instanceof Object);
console.log([] instanceof Object);
console.log(getType(drink));
console.log(getType(null));
```

## Imperative Iteration:

```javascript
const drink = {
id:"6565shgs",
name : "Alcohol",
price : {
sale : 99,
full : 126,
},
}
//for in
for (const prop in drink){
    if(Object.prototype.toString.call(drink[prop])=== "[object Object]") {
        for (const key in drink[prop]){
            console.log(key);
        }
    }
}

const drinkWithId = Object.create(drink);//Inherited
drinkWithId.id = "245452";
for(const prop in drinkWithId) {
    if(drinkWithId.hasOwnProperty(prop)){
        console.log(prop, drinkWithId[prop]);
    }
}
```

## Declarative Iteration:

```javascript
const drink = {
id:"6565shgs",
name : "Alcohol",
price : {
sale : 99,
full : 126,
},
}
Object.keys(drink).forEach(prop =>console.log(drink[prop]));
console.log(Object.entries(drink));
console.log(drink);
```



## The **this** Keyword

In a function definition, `this` refers to the "owner" of the function. In the example above, `this` is the **person object** that "owns" the  `fullName` function. In other words, `this.firstName` means the `firstName` property of **this object**.

## Accessing Object Methods

```
name = person.fullName();
```

> ## Do Not Declare Strings, Numbers, and Booleans as Objects!
>
> When a JavaScript variable is declared with the keyword "`new`", the variable is created as an object:
>
> ```
> var x = new String();        // Declares x as a String object
> var y = new Number();        // Declares y as a Number object
> var z = new Boolean();       // Declares z as a Boolean object
> ```
>
> 