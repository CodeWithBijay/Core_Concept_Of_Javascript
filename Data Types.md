## 🎖️🎖️Data Types : (JavaScript is Dynamic)🎖️🎖️

------

*Data types* are the classifications we give to the different kinds of data that we use in programming. In JavaScript, there are seven fundamental data types:



- *Number*: Any number, including numbers with decimals: `4`, `8`, `1516`, `23.42`.

- *String*: Any grouping of characters on your keyboard (letters, numbers, spaces, symbols, etc.) surrounded by single quotes: `' ... '` or double quotes `" ... "`. Though we prefer single quotes. Some people like to think of string as a fancy word for text.

- *Boolean*: This data type only has two possible values— either `true` or `false` (without quotes). It’s helpful to think of boolean as on and off switches or as the answers to a “yes” or “no” question.

- *Null*: This data type represents the intentional absence of a value, and is represented by the keyword `null` (without quotes).

- *Undefined*: This data type is denoted by the keyword `undefined` (without quotes). It also represents the absence of a value though it has a different use than `null`.

- *Symbol*: A newer feature to the language, symbols are unique identifiers, useful in more complex coding.

- *Object*: Collections of related data.

  ------

  

## 🏆🏆<u>Typeof:</u>🏆🏆

```javascript
typeof "John"              // Returns "string"
typeof 3.14                // Returns "number"
typeof true                // Returns "boolean"
typeof false               // Returns "boolean"
typeof x                   // Returns "undefined" (if x has no value)
```

```javascript
typeof {name:'John', age:34} // Returns "object"
typeof [1,2,3,4]             // Returns "object" (not "array",in JavaScript arrays are objects.)
typeof null                  // Returns "object"

typeof function myFunc(){}   // ⭐⭐Returns "function"
```

## Undefined 🆚 Null

> `undefined` and `null` are equal in value but different in type:

```javascript
typeof undefined           // undefined
typeof null                // object

null === undefined         // false
null == undefined          // true
```

