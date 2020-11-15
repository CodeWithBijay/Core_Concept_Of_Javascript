## Number

------

```javascript
console.log(parseInt("55px",10)); // 55
console.log(parseFloat("55.9999px")*10);//559.999
console.log(Number("55e10"));//550000000000
console.log(Number("55.9999"));//55.9999
console.log(9 + +"99.5555");//108.5555
```



```javascript
const anotherPrice = 9.33*100;
const anotherQuantity = 3;
console.log((anotherPrice*anotherQuantity)/100);
```

```javascript
console.log(Number(55));//55
console.log(Number("55"));//55
console.log(Number("44px"));//NaN
console.log(new Boolean("44px"));//NaN
```

```javascript
//NaN
const result = Number("55px");
console.log(isNaN(result));//true
console.log(isNaN("I am Bijay"));//true
console.log(Number.NaN);//NaN
console.log(Number.isNaN(result));//true
console.log(Number.isNaN("I am Bijay"));//false
console.log(Number.isNaN(Number.NaN));//true
console.log(Number.isInteger(66));//true
```



## Type Checking in Number:

```javascript
console.log(typeof 99.66);//Number
console.log(99 instanceof Number);//False
console.log(Number("99") instanceof Number);//False
console.log(new Number("99") instanceof Number);//true
console.log(Object.prototype.toString.call(99) === "[object Number]");//true
```

## Methods in Number

```javascript
console.log(Number.prototype);//0
console.log(parseFloat((91.56666).toFixed(4)));//91.5667
console.log((94.15458487).toPrecision(5));//"94.155"
console.log(new Number(99).valueOf());//99
```

