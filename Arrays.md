# `Arrays

JavaScript arrays are used to store multiple values in a single variable.

**JavaScript** does **not** support arrays with named indexes( Associative Arrays // Hashes ) . In JavaScript, **arrays** always use **numbered indexes**. 

#### <u>Creating an Array in JavaScript :</u>

```javascript
var cars = ["Saab", "Volvo", "BMW"];
```

```javascript
var cars = new Array("Saab", "Volvo", "BMW");
```

> Not to use constructor "new Array()".
>
> ```javascript
> var points = new Array(40); // Creates an array with 40 undefined elements !!!!
> 
> var points = [40];// Creates an array with an element "40" !!!!👍👍
> ```

### 🖕🖕Variables declared with the `const` keyword cannot be reassigned. However, elements in an array declared with `const` remain mutable. Meaning that we can change the contents of a `const` array, but cannot reassign a new array or a different value.

```
let condiments = ['Ketchup', 'Mustard', 'Soy Sauce', 'Sriracha'];
const utensils = ['Fork', 'Knife', 'Chopsticks', 'Spork'];
condiments[0] = 'Mayo';
console.log(condiments); //[ 'Mayo', 'Mustard', 'Soy Sauce', 'Sriracha' ]
condiments = ['Mayo'];
utensils[3] = 'Spoon';
console.log(utensils); //[ 'Fork', 'Knife', 'Chopsticks', 'Spoon' ]
```



#### <u>To check the Array:</u>

​       ✨✨ 

```javascript
console.log(typeof []);//"object"
console.log([] instanceof Array);//true
console.log(new Array() instanceof Array);//true
console.log(Array.isArray([0,1,2,3]));//true
console.log(Object.prototype.toString.call([]));//"[object Array]"
```



#### <u>Accessing The Element of an Array:</u>

```javascript
var name = cars[0];
```

#### <u>Changing an Array Element:</u>

```javascript

var cars = new Array("Saab", "Volvo", "BMW");
cars[0] = "Opel";//✔️✔️
cars["Saab"] = "Opel";//❌❌
```

##                                                                <u>Arrays are Object</u>

Arrays are a special type of objects. The `typeof` operator in JavaScript returns "object" for arrays.

------



##                                                                    Arrays Method:

### Converting Arrays to Strings:

```
// Using .toString()
var fruits = ["Banana", "Orange", "Apple", "Mango"];
console.log(fruits.toString());
```

```
// Using .join(' ');
var fruits = ["Banana", "Orange", "Apple", "Mango"];
console.log(fruits.join(" "));
```

### ➡️pop() Method   (removes the last element from an array):

```javascript
var fruits = ["Banana", "Orange", "Apple", "Mango"];
fruits.pop();              // Removes the last element ("Mango") from fruits
```

### ➡️push( ) Method   (adds a new element to an array (at the end)):

```javascript
var fruits = ["Banana", "Orange", "Apple", "Mango"];
fruits.push("Kiwi");       //  Adds a new element ("Kiwi") to fruits
```

### ➡️shift() Method  (removes the first array element and "shifts" all other elements to a lower index.):

```javascript
var fruits = ["Banana", "Orange", "Apple", "Mango"];
fruits.shift();//🌟🌟Return "Banana"
console.log(fruits);  // Removes the first element "Banana" from fruits
```

### ➡️unshift() Method (adds a new element to an array (at the beginning), and "unshifts" older elements):

```javascript
var fruits = ["Banana", "Orange", "Apple", "Mango"];
fruits.unshift("Lemon");// 🌟🌟Returns 5
console.log(fruits);// Adds a new element "Lemon" to fruits
```

### ➡️operator `delete`:

Since JavaScript arrays are objects, elements can be deleted by using the JavaScript operator `delete`:

```javascript
var fruits = ["Banana", "Orange", "Apple", "Mango"];
delete fruits[0];           // Changes the first element in fruits to undefined
```

### ➡️splice() Method (used to add new items to an array)  ||  (to remove elements without leaving "holes" in the array):

```javascript
var fruits = ["Banana", "Orange", "Apple", "Mango"];
console.log(fruits.splice(2, 0, "Lemon", "Kiwi"));
console.log(fruits);//
```

- The first parameter (2) defines the position **where** new elements should be **added** (spliced in).

- The second parameter (0) defines **how many** elements should be **removed**.

- The rest of the parameters ("Lemon" , "Kiwi") define the new elements to be **added**.

- The `splice()` method returns an array with the deleted items:

```javascript
var fruits = ["Banana", "Orange", "Apple", "Mango"];
fruits.splice(0, 1);        // Removes the first element of fruits
```

- The first parameter (0) defines the position where new elements should be **added** (spliced in).

- The second parameter (1) defines **how many** elements should be **removed**.

- The rest of the parameters are omitted. No new elements will be added.

### ➡️concat() Method (creates a new array by merging (concatenating) existing arrays:):

```javascript
//Concat Two Arrays
var myGirls = ["Cecilie", "Lone"];
var myBoys = ["Emil", "Tobias", "Linus"];
var myChildren = myGirls.concat(myBoys);   // Concatenates (joins) myGirls and myBoys
```

```javascript
//Concat Three Arrays
var arr1 = ["Cecilie", "Lone"];
var arr2 = ["Emil", "Tobias", "Linus"];
var arr3 = ["Robin", "Morgan"];
var myChildren = arr1.concat(arr2, arr3);   // Concatenates arr1 with arr2 and arr3
```

```javascript
//Concat string as a Argument
var arr1 = ["Emil", "Tobias", "Linus"];
var myChildren = arr1.concat("Peter"); 
```

### ➡️slice() Method ( slices out a piece of an array into a new array):

```javascript
var fruits = ["Banana", "Orange", "Lemon", "Apple", "Mango"];
var citrus = fruits.slice(1);
```

```javascript
var fruits = ["Banana", "Orange", "Lemon", "Apple", "Mango"];
var citrus = fruits.slice(1, 3);//["Orange", "Lemon"]
```

------

## Destructing of Array:

```javascript
const drinks = [["Lemonade", 99], ["Lime", 99],["Peach",89]];
const [one, [, b],...rest] = drinks;
console.log(one, b, rest);//["Lemonade", 99] 99 [["Peach", 89]]
```

------

## Adding element to array in New Way:

```javascript
var fruits = ["Banana", "Orange", "Lemon", "Apple", "Mango"];
var fruitsIn = ["kiwi",...fruits];
console.log(fruitsIn);//["kiwi", "Banana", "Orange", "Lemon", "Apple", "Mango"]
```

------

## Finding An Array

```javascript
const drinks = ["Lemonade","Lime","Peach"];
const index = drinks.indexOf("Lime");
console.log(index);             //1
if(index !== -1){
console.log(drinks[index]);
}

const included = drinks.includes("Peach");
console.log(included);//true

const drinksWithId = [
{ id: 1, name: "Lemonade" },
{ id: 2, name: "Lime" },
{ id: 3, name: "Peach" },
];
const idIndex = drinksWithId.findIndex(value => value.name === "Peach");
console.log(drinksWithId[idIndex]);

const foundItem = drinksWithId.find(value => value.name === "Peach");
console.log(foundItem);
```

------

## Shallow and Deep Array cloning

```javascript
const drinks = [["Lemonade", 99], ["Lime", 99],["Peach",89]];
const drinksClone = [...drinks];
const drinksClone = drinks.slice();
const drinksClone = Array.from(drinks);
const drinksClone = JSON.prase(JSON.stringify(drinks));
drinksClone[0][1] = 1000;
console.log(drinks);
```



------

## Array Sorts

### sort() Method:(orts an array alphabetically)

```javascript
var fruits = ["Banana", "Orange", "Apple", "Mango"];
fruits.sort();        // Sorts the elements of fruits
```

### reverse()  Method (reverses the elements in an array)

```javascript
var fruits = ["Banana", "Orange", "Apple", "Mango"];
fruits.sort();        // First sort the elements of fruits
fruits.reverse();     // Then reverse the order of the elements
```

