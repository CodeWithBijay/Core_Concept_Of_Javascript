## String

------

JavaScript strings are used for storing and manipulating text.

```javascript
var carName1 = "Volvo XC60";  // Double quotes
var carName2 = 'Volvo XC60';  // Single quote
```



## 💛 String Length

```javascript
var txt = "ABCDEFGHIJKLMNOPQRSTUVWXYZ";
var sln = txt.length;
```

```javascript
var txt = "ABCDEFGHIJKLMNOPQRSTUVWXYZ";
console.log(txt['length']);
```



## Escape Character

| Code | Result | Topic        |
| ---- | ------ | ------------ |
| \\'  | '      | Single quote |
| \\"  | "      | Double quote |
| \\\  | \      | Backslash    |

| Code | Result               |
| ---- | -------------------- |
| \b   | Backspace            |
| \f   | Form Feed            |
| \n   | New Line             |
| \r   | Carriage Return      |
| \t   | Horizontal Tabulator |
| \v   | Vertical Tabulator   |

## Strings Can be Objects

 JavaScript strings are primitive values, created from literals:

```javascript
var firstName = "John";
```

But strings can also be defined as objects with the keyword `new`:

```javascript
var firstName = new String("John");
```

```javascript
var x = "John";
var y = new String("John");

// typeof x will return string
// typeof y will return object
//Don't create strings as objects. It slows down execution speed.
The new keyword complicates the code. This can produce some unexpected results:
```

## 😒😒 String as a Objects cannot be compared:😒😒

```javascript
var x = new String("John");             
var y = new String("John");

// (x == y) is false because x and y are different objects
// (x === y) is false because x and y are different objects
```

## Type-Checking in String

```javascript
console.log(typeof 'Bijay');
console.log('Bijay' instanceof String);
console.log(new String('Bijay') instanceof String);
console.log(String('Bijay') instanceof String);
console.log(Object.prototype.toString.call('Bijay'));
```

## Some Methods in String

```javascript
console.log(String.prototype);

console.log('Bijay'.indexOf('B'));       // 0
console.log('Bijay'.includes('B'));       //true
console.log('Bijay'.replace('ijay', 'J'));  //BJ
console.log('Bijay'.slice(0,-2));         //Bij
console.log('Bijay'.split('i')[0]);       //B
console.log('  Bijay  '.trim());          //Bijay
console.log('Bijay'.concat(" Paudel"));  //Bijay Paudel
```

