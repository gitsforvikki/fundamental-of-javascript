# fundamental-of-javascrips

## sort() methods

> Array of Strings
- Let's start with strings:


When we use the `sort( )` method, elements will be sorted in ascending order (A to Z) by default:
```javascript
const teams = ['Real Madrid', 'Manchester Utd', 'Bayern Munich', 'Juventus'];

teams.sort(); 

// ['Bayern Munich', 'Juventus', 'Manchester Utd', 'Real Madrid']
```
If you prefer to sort the array in descending order, you need to use the `reverse( )` method instead:

> Array of Numbers
    Sorting numbers is unfortunately not that simple. If we apply the sort method directly to a numbers array, we will see an unexpected result:

```javascript
const numbers = [3, 23, 12];

numbers.sort(); // --> 12, 23, 3
```
> Why the `sort( )` method isn't working for numbers
    - Actually it is working, but this problem happens because JavaScript sorts numbers alphabetically. Let me explain this in detail.
    
- solution

All we need to is using the compare function inside the sort( ) method:
```javascript
const numbers = [3, 23, 12];

numbers.sort(function(a, b){return a - b}); // --> 3, 12, 23
```

> If we want to sort the numbers in descending order, this time we need to subtract the second parameter (b) from the first one (a):

```javascript
const numbers = [3, 23, 12];

numbers.sort(function(a, b){return b - a}); // --> 23, 12, 3
```

## reverce() mothod

Array will modified when the reverse method is applied to it.

If you do not want the array to be modified, you can clone it before applying the reverse. The reverse method also returns the reversed array, so you can assign that array to a variable.

Here's how to duplicate and reverse an array:

``` javascript

const array = [1, 2, 3, 4]

const reversed = [...array].reverse()

console.log(reversed)
// [ 4, 3, 2, 1 ]

console.log(array)
// [ 1, 2, 3, 4 ]

```

## push() method
 The `push()` method will add one or more arguments at the end of an array in JavaScript.
 
 ```javascript
 let arr = [0, 1, 2, 3];
arr.push(4);
console.log(arr); // [0, 1, 2, 3, 4]
```

The `push()` method also returns the new length of the array.

```javascript
let arr = [0, 1, 2, 3];
let newLength = arr.push(4);
console.log(newLength); // 5
```
```javascript

let arr1 = [0, 1, 2, 3];
let arr2 = [4, 5, 6, 7];
arr1.push(...arr2);
console.log(arr1); // [0, 1, 2, 3, 4, 5, 6, 7]
```
## pop() method

The `pop()` method removes the last element from an array and returns that element. This method changes the length of the array.

```javascript

const plants = ['broccoli', 'cauliflower', 'cabbage', 'kale', 'tomato'];

console.log(plants.pop());
// Expected output: "tomato"

console.log(plants);
// Expected output: Array ["broccoli", "cauliflower", "cabbage", "kale"]

plants.pop();

console.log(plants);
// Expected output: Array ["broccoli", "cauliflower", "cabbage"]
```
## shift() method
The `shift()` method removes the first element from an array and returns that removed element. This method changes the length of the array.

The removed element from the array; undefined if the array is empty.


```javascript
const array1 = [1, 2, 3];

const firstElement = array1.shift();

console.log(array1);
// Expected output: Array [2, 3]

console.log(firstElement);
// Expected output: 1

```
```javascript
//using shift() method in while loop
const names = ["Andrew", "Tyrone", "Paul", "Maria", "Gayatri"];

while (typeof (i = names.shift()) !== "undefined") {
  console.log(i);
}
// Andrew, Tyrone, Paul, Maria, Gayatri
```

## unsift() method
    The unshift() method adds one or more elements to the beginning of an array and returns the new length of the array.
    The new length property of the object upon which the method was called.
//syntax

unshift(element0)
unshift(element0, element1)
unshift(element0, element1, /* … ,*/ elementN)

```javascript
const array1 = [1, 2, 3];

console.log(array1.unshift(4, 5));
// Expected output: 5

console.log(array1);
// Expected output: Array [4, 5, 1, 2, 3]
```
```javascript
let arr = [4, 5, 6];

arr.unshift(1, 2, 3);
console.log(arr);
// [1, 2, 3, 4, 5, 6]

arr = [4, 5, 6]; // resetting the array

arr.unshift(1);
arr.unshift(2);
arr.unshift(3);

console.log(arr);
// [3, 2, 1, 4, 5, 6]
```
## concat() method
The `concat()` method is used to merge two or more arrays. This method does not change the existing arrays, but instead returns a new array.

```javascript
const letters = ["a", "b", "c"];
const numbers = [1, 2, 3];

const alphaNumeric = letters.concat(numbers);
console.log(alphaNumeric);
// results in ['a', 'b', 'c', 1, 2, 3]
```

```javascript
//The following code concatenates three arrays:


const num1 = [1, 2, 3];
const num2 = [4, 5, 6];
const num3 = [7, 8, 9];

const numbers = num1.concat(num2, num3);

console.log(numbers);
// results in [1, 2, 3, 4, 5, 6, 7, 8, 9]
```

## join() method

The join() method creates and returns a new string by concatenating all of the elements in an array (or an array-like object), separated by commas or a specified separator string. 

```javascript
const a = ["Wind", "Water", "Fire"];
a.join(); // 'Wind,Water,Fire'
a.join(", "); // 'Wind, Water, Fire'
a.join(" + "); // 'Wind + Water + Fire'
a.join(""); // 'WindWaterFire'
```
## slice() method

The slice() method can be used to create a copy of an array or return a portion of an array. It is important to note that the slice() method does not alter the original array but instead creates a shallow copy.

Here is the basic syntax:

slice(optional start parameter, optional end parameter)

```javascript
const cities = ["Tokyo","Cairo","Los Angeles","Paris","Seattle"];
cities.slice(); //["Tokyo","Cairo","Los Angeles","Paris","Seattle"]

//use slice with first parameter
const newCityArr = cities.slice(2);

console.log(newCityArr); //["Los Angeles","Paris","Seattle"]

//If the start parameter is greater than the last index of the array, then an empty array will be returned.
const newCityArr = cities.slice(5);
console.log(newCityArr); //[]

```

> If an end position is specified, then the slice() method will extract elements from the start position up to the end position. The end position will not be included in the extracted elements for the new array.

```javascript
const cities = ["Tokyo","Cairo","Los Angeles","Paris","Seattle"];

const newCityArr = cities.slice(2,4);
console.log(newCityArr); //["Los Angeles","Paris"]
```
## splice()  method

Unlike the slice() method, the splice() method will change the contents of the original array. The splice() method is used to add or remove elements of an existing array and the return value will be the removed items from the array.

If nothing was removed from the array, then the return value will just be an empty array.

- Here is the basic syntax.

> splice(start, optional delete count, optional items to add)


```javascript

const food = ['pizza', 'cake', 'salad', 'cookie'];
food.splice(1,0,"burrito");
console.log(food); //['pizza','burrito', 'cake', 'salad', 'cookie']

```
If we  console.log(food.splice(1,0,"burrito")), then we would get back an empty array because nothing was removed from our array.

```javascript
const food = ['pizza', 'cake', 'salad', 'cookie'];

let newArr = food.splice(2,1);
console.log(newArr); //[salad]
console.log(food); //['pizza', 'cake',  'cookie']
```

### Conclusion
The slice and splice array methods might seem similar to each other, but there are a few key differences.

The slice() method can be used to create a copy of an array or return a portion of an array. It is important to note that the slice() method does not alter the original array but instead creates a shallow copy.

## indexof() method

The indexOf() method returns the first index at which a given element can be found in the array, or -1 if it is not present.

- syntax
> indexOf(searchElement)

> indexOf(searchElement, fromIndex)

```javascript
const beasts = ['ant', 'bison', 'camel', 'duck', 'bison'];

console.log(beasts.indexOf('bison'));
// Expected output: 1

// Start from index 2
console.log(beasts.indexOf('bison', 2));
// Expected output: 4

console.log(beasts.indexOf('giraffe'));
// Expected output: -1

```

```javascript
const array = [2, 9, 2, 9];
array.indexOf(2); // 0
array.indexOf(7); // -1
array.indexOf(9, 2); // 3
array.indexOf(2, -1); // -1
array.indexOf(2, -3); // 0

```
## lastIndexOf() method
The lastIndexOf() method returns the last index at which a given element can be found in the array, or -1 if it is not present. The array is searched backwards, starting at fromIndex.

- syntax
> lastIndexOf(searchElement)

> lastIndexOf(searchElement, fromIndex)


```javascript
const animals = ['Dodo', 'Tiger', 'Penguin', 'Dodo'];

console.log(animals.lastIndexOf('Dodo'));
// Expected output: 3

console.log(animals.lastIndexOf('Tiger'));
// Expected output: 1
```

```javascript
const numbers = [2, 5, 9, 2];
numbers.lastIndexOf(2); // 3
numbers.lastIndexOf(7); // -1
numbers.lastIndexOf(2, 3); // 3
numbers.lastIndexOf(2, 2); // 0
numbers.lastIndexOf(2, -2); // 0
numbers.lastIndexOf(2, -1); // 3

```
## find() method
The `find()` method returns the first element in the provided array that satisfies the provided testing function. If no values satisfy the testing function, undefined is returned.

```javascript
const array1 = [5, 12, 8, 130, 44];

const found = array1.find(element => element > 10);

console.log(found);
// Expected output: 12
```
```javascript
const inventory = [
  { name: "apples", quantity: 2 },
  { name: "bananas", quantity: 0 },
  { name: "cherries", quantity: 5 },
];

function isCherries(fruit) {
  return fruit.name === "cherries";
}

console.log(inventory.find(isCherries));
// { name: 'cherries', quantity: 5 }

const result = inventory.find(({ name }) => name === "cherries");

console.log(result); // { name: 'cherries', quantity: 5 }
Copy to Clipboard
```

## every() method
The `every()` method tests whether all elements in the array pass the test implemented by the provided function. It returns a Boolean value.


```javascript
const isBelowThreshold = (currentValue) => currentValue < 40;

const array1 = [1, 30, 39, 29, 10, 13];

console.log(array1.every(isBelowThreshold));
// Expected output: true
```

```javascript
//The following example tests whether all elements in the array are bigger than 10.

function isBigEnough(element, index, array) {
  return element >= 10;
}
[12, 5, 8, 130, 44].every(isBigEnough); // false
[12, 54, 18, 130, 44].every(isBigEnough); // true
```


```javascript
//Check if one array is a subset of another array
const isSubset = (array1, array2) =>
  array2.every((element) => array1.includes(element));

console.log(isSubset([1, 2, 3, 4, 5, 6, 7], [5, 7, 6])); // true
console.log(isSubset([1, 2, 3, 4, 5, 6, 7], [5, 8, 7])); // false
```

## include() mothod
The `includes()` method determines whether an array includes a certain value among its entries, returning true or false as appropriate.

```javascript
const array1 = [1, 2, 3];

console.log(array1.includes(2));
// Expected output: true

const pets = ['cat', 'dog', 'bat'];

console.log(pets.includes('cat'));
// Expected output: true

console.log(pets.includes('at'));
// Expected output: false
```

- Using `includes()` on sparse arrays
You can search for undefined in a sparse array and get true.
```javascript
console.log([1, , 3].includes(undefined)); // true

```






##Map, Reduce, and Filter  JS Array Functions

Map, reduce, and filter are all array methods in JavaScript. Each one will iterate over an array and perform a transformation or computation.
## map() method
The `map()` method is used for creating a new array from an existing one, applying a function to each one of the elements of the first array.
> syntax
```javascript
var new_array = arr.map(function callback(element, index, array) {
    // Return value for new_array
}[, thisArg])
```
> Example

```javascript
let num = [1, 2, 41, 45, 20];

function binary(x) {
  return x.toString(2);
}
let newNum = num.map(binary);
console.log(newNum);

```
```javascript
const numbers = [1, 2, 3, 4];
const doubled = numbers.map(item => item * 2);
console.log(doubled); // [2, 4, 6, 8]

```
## filter() array
The `filter()` method takes each element in an array and it applies a conditional statement against it. If this conditional returns true, the element gets pushed to the output array. If the condition returns false, the element does not get pushed to the output array.

```javascript
const numbers = [1, 2, 3, 4];
const evens = numbers.filter(item => item % 2 === 0);
console.log(evens); // [2, 4]
```

```javascript
const students = [
  { name: 'Quincy', grade: 96 },
  { name: 'Jason', grade: 84 },
  { name: 'Alexis', grade: 100 },
  { name: 'Sam', grade: 65 },
  { name: 'Katie', grade: 90 }
];

const studentGrades = students.filter(student => student.grade >= 90);
return studentGrades; // [ { name: 'Quincy', grade: 96 }, { name: 'Alexis', grade: 100 }, { name: 'Katie', grade: 90 } ]
```
## reduce() method
The `reduce()` method reduces an array of values down to just one value. To get the output value, it runs a reducer function on each element of the array.

The callback argument is a function that will be called once for every item in the array. This function takes four arguments, but often only the first two are used.

>syntax

```javascript
arr.reduce((acc , curr)=>{
        //reduce logic
} , initial_value_of_acc);
```
- accumulator(acc) : the returned value of the previous iteration
- currentValue(curr) : the current item in the array

### Examples
The following example adds every number together in an array of numbers.
```javascript
const numbers = [1, 2, 3, 4];
const sum = numbers.reduce(function (result, item) {
  return result + item;
}, 0);
console.log(sum); // 10
```

```javascript
//find out max of an array
let numArray = [12, 76, 50, 35, 66];
let maximum = numArray.reduce((max, current) => {
  max = current > max ? current : max;
  return max;
});
console.log(maximum);

```
In the next example, `reduce()` is used to transform an array of strings into a single object that shows how many times each string appears in the array. Notice this call to reduce passes an empty object {} as the initialValue parameter. This will be used as the initial value of the accumulator (the first argument) passed to the callback function.

```javascript
var pets = ['dog', 'chicken', 'cat', 'dog', 'chicken', 'chicken', 'rabbit'];

var petCounts = pets.reduce(function(obj, pet){
    if (!obj[pet]) {
        obj[pet] = 1;
    } else {
        obj[pet]++;
    }
    return obj;
}, {});

console.log(petCounts); 

/*
Output:
 { 
    dog: 2, 
    chicken: 3, 
    cat: 1, 
    rabbit: 1 
 }
 */
 ```
 
 ```javascript
 
 let users =
 
 [{"first_name":"Margot","last_name":"Liddicoat","email":"mliddicoat0@github.com","gender":"Female","age":11},
{"first_name":"Mara","last_name":"Bendell","email":"mbendell1@cnet.com","gender":"Female","age":99},
{"first_name":"Roch","last_name":"O'Brogan","email":"robrogan2@wired.com","gender":"Polygender","age":62},
{"first_name":"Bayard","last_name":"Weeden","email":"bweeden3@cafepress.com","gender":"Genderfluid","age":66},
{"first_name":"Loralie","last_name":"Alexsandrov","email":"lalexsandrov4@t-online.de","gender":"Female","age":93}];


 //find the first name of all the people whose age greater than or equals to  50

let people = users.filter((user) => {
  if (user.age >= 50) {
    return user.first_name;
  }
});
let result = people.map((each) => {
  return each.first_name;
});
console.log(result);

//i can use filter and map together known as `chaining`
let employees = users
  .filter((user) => user.age > 50)
  .map((user) => {
    return user.first_name;
  });
console.log(employees);
```
## loops in javascript

- while loop
- do-while loop
- for loop
- for-in loop
- for-of loop

> while loop


        Before the statement is executed, condition is tested. If it evaluates to true, then the statement is executed. As long as condition is true, the         statement continues to execute. 
```javascript
    let e = 0;
    while (e < 4) {
    console.log(e);
     e++;
    }
```
> do-while loop


The first thing that happens in this loop is the statement is executed. Once that happens, condition is checked. If condition evaluates to true, the statement executes again. 

```javascript
let booksRead = 10;
do {
 console.log(`I read ${booksRead} books this year`);
 booksRead++;
} while (booksRead < 14);
```



> for loop
 
 - syntax
    for (initialExpression; conditionExpression; incrementExpression) {
     statement
    }


```javascript
    for (let i = 1; i <= 5; i++) {
    console.log(“I can count to “ + i)
```

> for...in loop


A for…in loop is used with an object in JavaScript. It’s structured like the following:

```javascript
for (variable in object) {
 statement
}
```

```javascript
//example
const foodIAte = {
 breakfast: ‘eggs’,
 lunch: ‘salad’,
 dinner: ‘pizza’
};
for(const meal in foodIAte) {
 console.log(`For ${meal}, I ate ${foodIAte[meal]}.`);
};


//output
//For breakfast, I ate eggs.
//For lunch, I ate salad.
//For dinner, I ate pizza.
```

> For…of loops


The last loop is the for…of loop. The for…of loop can be used with iterable objects, which includes arrays, maps, sets, strings, and more. It’s structured like the following:

```javascript
const string = “cat”;
for (const value of string) {
 console.log(value);
}

//output
// c a t
```

```javascript
const array = [5, 10, 15];
for (const value of array) {
 console.log(value);
}

//output
//5 10 15
```

## this keyword in javascript

### this Context
When used in a function, the this keyword simply points to an object to which it is bound. It answers the question of where it should get some value or data from:

```javascript
function alert() { 
  console.log(this.name + ' is calling'); 
}
```
A function with a "this" reference
In the function above, the this keyword is referring to an object to which it is bound so it gets the `"name"` property from there.

But how do you know which object the function is bound to? How do you find out what this is referring to?

To do so, we need to take a detailed look at how functions are bound to objects.

- Types of Binding in JavaScript



There are generally four kinds of bindings:

- Default Binding
- Implicit Binding
- Explicit Binding
- Constructor Call Binding


### Default Binding in JavaScript
One of the first rules to remember is that if the function housing a this reference is a standalone function, then that function is bound to the global object.


```javascript
function alert() { 
  console.log(this.name + ' is calling'); 
}

const name = 'Kingsley'; 
alert(); // Kingsley is calling

```

As you can see, `name()` is a standalone, unattached function, so it is bound to the global scope. As a result, the `this.name` reference resolves to the global variable `const name = 'Kingsley'` .

This rule, however, doesn't hold if `name()` were to be defined in strict mode:

```javascript
function alert() { 
  'use strict'; 
  console.log(this.name + ' is calling'); 
}

const name = 'Kingsley'; 
alert(); // TypeError: `this` is `undefined`

```
### Implicit Binding in JavaScript

According to the binding rule in JavaScript, a function can use an object as its context only if that object is bound to it at the call site. This form of binding is known as implicit binding.

here it is what i mean by it

```javascript
function alert() { 
  console.log(this.age + ' years old'); 
}

const myObj = {
  age: 22,
  alert: alert
}

myObj.alert() // 22 years old
```
when you call a function using dot notation, this is implicitly bound to the object the function is being called from.

Let's look at another example:

```javascript
function alert() { 
  console.log(this.age + ' years old'); 
}

const myObj = {
  age: 22,
  alert: alert,
  nestedObj: {
    age: 26,
    alert: alert
  }
}

myObj.nestedObj.alert(); // 26 years old
myObj.alert(); // `this` is bound to `myObj` -- 22 years old

```

### Explicit binding in JavaScript

if we want to force a function to use an object as its context without putting a property function reference on the object?

We have two utility methods to achieve this: `call()` and `apply()` .



To explicitly bind a function call to a context, you simply have to invoke the call() on that function and pass in the context object as parameter:

```javascript
function alert() { 
  console.log(this.age + ' years old'); 
}

const myObj = {
  age: 22
}

alert.call(myObj); // 22 years old

```


```javascript
//this is called hard binding
function alert() { 
  console.log(this.age); 
} 

const myObj = { 
  age: 22 
}; 

const bar = function() { 
  alert.call(myObj); 
}; 

bar(); // 22
setTimeout(bar, 100); // 22 
// a hard-bound `bar` can no longer have its `this` context overridden 
bar.call(window); // still 22

```





## call, apply and bind methods

we want to force a function to use an object as its context without putting a property function reference on the object?

We have two utility methods to achieve this: `call()` and `apply()` .
## definition

- call() method

Call is a function that helps you change the context of the invoking function. In layperson's terms, it helps you replace the value of this inside a function with whatever value you want.

- apply() method


Apply is very similar to the call function. The only difference is that in apply you can pass an array as an argument list.


```javascript
//example

var pokemon = {
    firstname: 'Pika',
    lastname: 'Chu ',
    getPokeName: function() {
        var fullname = this.firstname + ' ' + this.lastname;
        return fullname;
    }
};

var pokemonName = function(snack, hobby) {
    console.log(this.getPokeName() + ' loves ' + snack + ' and ' + hobby);
};

pokemonName.call(pokemon,'sushi', 'algorithms'); // Pika Chu  loves sushi and algorithms
pokemonName.apply(pokemon,['sushi', 'algorithms']); // Pika Chu  loves sushi and algorithms

```
- bind() method
Bind is a function that helps you create another function that you can execute later with the new context of this that is provided.

```javascript

//example
var pokemon = {
    firstname: 'Pika',
    lastname: 'Chu ',
    getPokeName: function() {
        var fullname = this.firstname + ' ' + this.lastname;
        return fullname;
    }
};

var pokemonName = function() {
    console.log(this.getPokeName() + 'I choose you!');
};

var logPokemon = pokemonName.bind(pokemon); // creates new object and binds pokemon. 'this' of pokemon === pokemon now

logPokemon(); // 'Pika Chu I choose you!'

```

```javascript

var pokemon = {
    firstname: 'Pika',
    lastname: 'Chu ',
    getPokeName: function() {
        var fullname = this.firstname + ' ' + this.lastname;
        return fullname;
    }
};

var pokemonName = function(snack, hobby) {
    console.log(this.getPokeName() + 'I choose you!');
    console.log(this.getPokeName() + ' loves ' + snack + ' and ' + hobby);
};

var logPokemon = pokemonName.bind(pokemon); // creates new object and binds pokemon. 'this' of pokemon === pokemon now

logPokemon('sushi', 'algorithms'); // Pika Chu  loves sushi and algorithms

```

## Javascript predefined core objects

The predefined core objects are Array , Boolean , Date , Function , Math , Number , RegExp , and String .


## Math object

- Math.floor()


The Math.floor() static method always rounds down and returns the largest integer less than or equal to a given number.
```javascript
console.log(Math.floor(5.95));
// Expected output: 5

console.log(Math.floor(5.05));
// Expected output: 5

console.log(Math.floor(5));
// Expected output: 5

console.log(Math.floor(-5.05));
// Expected output: -6

```

- Math.log()


The Math.log() static method returns the natural logarithm (base e) of a number.

```javascript
function getBaseLog(x, y) {
  return Math.log(y) / Math.log(x);
}

// 2 x 2 x 2 = 8
console.log(getBaseLog(2, 8));
// Expected output: 3

// 5 x 5 x 5 x 5 = 625
console.log(getBaseLog(5, 625));
// Expected output: 4

```

- Math.log10()


The Math.log10() static method returns the base 10 logarithm of a number. 

- Math.max()


The Math.max() static method returns the largest of the numbers given as input parameters, or -Infinity if there are no parameters.
```javascript
console.log(Math.max(1, 3, 2));
// Expected output: 3

console.log(Math.max(-1, -3, -2));
// Expected output: -1

const array1 = [1, 3, 2];

console.log(Math.max(...array1));
// Expected output: 3

```


- Math.min()
The Math.min() static method returns the smallest of the numbers given as input parameters, or Infinity if there are no parameters.
```javascript
console.log(Math.min(2, 3, 1));
// Expected output: 1

console.log(Math.min(-2, -3, -1));
// Expected output: -3

const array1 = [2, 3, 1];

console.log(Math.min(...array1));
// Expected output: 1
```

- Math.pow()


The Math.pow() static method returns the value of a base raised to a power. 

That is

𝙼𝚊𝚝𝚑.𝚙𝚘𝚠 ( 𝚡 , 𝚢 ) = x ^y

```javascript
console.log(Math.pow(7, 3));
// Expected output: 343

console.log(Math.pow(4, 0.5));
// Expected output: 2

console.log(Math.pow(7, -2));
// Expected output: 0.02040816326530612
//                  (1/49)

console.log(Math.pow(-7, 0.5));
// Expected output: NaN

```

- Math.random()


The Math.random() static method returns a floating-point, pseudo-random number that's greater than or equal to 0 and less than 1

```javascript
function getRandomInt(max) {
  return Math.floor(Math.random() * max);
}

console.log(getRandomInt(3));
// Expected output: 0, 1 or 2

console.log(getRandomInt(1));
// Expected output: 0

console.log(Math.random());
// Expected output: a number from 0 to <1


```

- Math.round()


The Math.round() static method returns the value of a number rounded to the nearest integer.
```javascript
console.log(Math.round(0.9));
// Expected output: 1

console.log(Math.round(5.95), Math.round(5.5), Math.round(5.05));
// Expected output: 6 6 5

console.log(Math.round(-5.05), Math.round(-5.5), Math.round(-5.95));
// Expected output: -5 -5 -6

```

## Axios

Axios is an HTTP client library based on promises. It makes sending asynchronous HTTP requests to REST endpoints easier and helps you perform CRUD operations.

Axios used to make GET, POST, and DELETE API requests in React. I mean, how i retrieve data from an API, add data to the API, and then delete data from our API.


### Why Axios?

Here are some reasons:

- Axios uses XMLHttpRequest under the hood, and it is widely supported by most browsers. 


- When sending requests, Axios automatically signifies the data, unlike fetch(), which requires us to do it manually.

- Unlike the Fetch API, which requires you to check the status code and throw the error yourself, Axios has better error handling and can throw 400 and 500 range errors.


### How to Get Started with Axios in React

- How to Create the Axios Instance

it's a good idea to create an Axios instance. It's not required, but it saves us time.

To create an instance, we'll use the `.create()` method, which lets us specify information such as the URL and possibly headers:


```javascript
import axios from "axios";

const client = axios.create({
  baseURL: "https://jsonplaceholder.typicode.com/posts" 
});
```


### How to Make a GET Request with Axios in React

We'll use the variable and then attach the .get() method to make a GET request to our endpoint/API. Then we'll use a .then() callback to get back all the response data, because we already have an Axios instance that holds the baseURL assigned to a variable (client).

Using the .data property, we obtain the response data, which is the actual data from the response object.

```javascript
const App = () => {
   const [posts, setPosts] = useState([]);

   useEffect(() => {
      client.get('?_limit=10').then((response) => {
         setPosts(response.data);
      });
   }, []);

   return (
      // ...react code to consume the response from axios
   );
};

export default App;
```

### How to Make a POST Request with Axios in React

It works similarly to a `GET` request, except that the function created to perform this task will be triggered when the form is submitted or otherwise.

This takes an object to send the data in and also adds the data to the state by spreading the previous data and then adding the new data:


```javascript

const App = () => {
   const [title, setTitle] = useState('');
   const [body, setBody] = useState('');
   const [posts, setPosts] = useState([]);

   // ...

   const handleSubmit = (e) => {
      e.preventDefault();
      addPosts(title, body);
   };

   const addPosts = (title, body) => {
      client
         .post('', {
            title: title,
            body: body,
         })
         .then((response) => {
            setPosts([response.data, ...posts]);
         });
      setTitle('');
      setBody('');
   };
   
   return (
      // ...
   );
};

export default App;
```

When the form is submitted, we call the `handleSubmit()` function, which prevents the page from reloading. It also calls the main function `addPosts()` by passing the data entered into the form as a parameter.

### How to Perform a DELETE Request in React

For this, we will use the DELETE method in conjunction with the client variable where we initialized Axios. This is how the request will look:

```javascript

const App = () => {
   const [posts, setPosts] = useState([]);

   // ...

   const deletePost = (id) => {
      client.delete(`${id}`);
      setPosts(
         posts.filter((post) => {
            return post.id !== id;
         })
      );
   };

   return (
      // ...
   );
};

export default App;

```

Basically, there is a `onClick()` method on the delete button that triggers the deletePost() method. We passed it the ID of the particular post we are attempting to delete so we can identify the post.

### How to Make Requests in React with `Async/Await`

we can use async/await to write less code and avoid the .then chaining, which is much more difficult to understand.

To use async/await, first call async in the function. Then add the await syntax in front of the function when making a request and expecting a response to wait until the promise settles with the result.

When we use async/await, all of our Axios requests will look like this:

```javascript
const App = () => {
   const [title, setTitle] = useState('');
   const [body, setBody] = useState('');
   const [posts, setPosts] = useState([]);

    // GET with Axios
   useEffect(() => {
      const fetchPost = async () => {
         let response = await client.get('?_limit=10');
         setPosts(response.data);
      };
      fetchPost();
   }, []);

   // DELETE with Axios
   const deletePost = async (id) => {
      await client.delete(`${id}`);
      setPosts(
         posts.filter((post) => {
            return post.id !== id;
         })
      );
   };
    
   // handle form submission
   const handleSubmit = (e) => {
      e.preventDefault();
      addPosts(title, body);
   };

   // POST with Axios
   const addPosts = async (title, body) => {
      let response = await client.post('', {
         title: title,
         body: body,
      });
      setPosts([response.data, ...posts]);
      setTitle('');
      setBody('');
   };

   return (
      // ...
   );
};

```

### How to Handle Errors in Axios
When consuming data from an API, it is always recommended that we handle errors to help show the type of error we get. These errors may occur as a result of us passing incorrect data, making a request to the incorrect API, or experiencing a network error.

We can handle errors in Axios by using the `.then()` and `.catch()` methods, or by using the `try...catch` block for `async/await` Axios requests.

You can implement this by attaching a .catch() method to the .then() method to handle errors. Suppose the .then() method fails:

```javascript
useEffect(() => {
  client
     .get('?_limit=10')
     .then((response) => {
        setPosts(response.data);
     })
     .catch((error) => {
        console.log(error);
     });
}, []);
```

 async/await scenario, the try...catch block will look like this
 
 ```javascript
 useEffect(() => {
  const fetchPost = async () => {
     try {
        let response = await client.get('?_limit=10');
        setPosts(response.data);
     } catch (error) {
        console.log(error);
     }
  };
  fetchPost();
}, []);
```
