# fundamental-of-javascrips

## sort() methods

Array of Strings
Let's start with strings:

const teams = ['Real Madrid', 'Manchester Utd', 'Bayern Munich', 'Juventus'];

When we use the sort( ) method, elements will be sorted in ascending order (A to Z) by default:

teams.sort(); 

// ['Bayern Munich', 'Juventus', 'Manchester Utd', 'Real Madrid']
If you prefer to sort the array in descending order, you need to use the reverse( ) method instead:

Array of Numbers
    Sorting numbers is unfortunately not that simple. If we apply the sort method directly to a numbers array, we will see an unexpected result:


const numbers = [3, 23, 12];

numbers.sort(); // --> 12, 23, 3

Why the sort( ) method isn't working for numbers
    Actually it is working, but this problem happens because JavaScript sorts numbers alphabetically. Let me explain this in detail.
    
solution

All we need to is using the compare function inside the sort( ) method:

const numbers = [3, 23, 12];

numbers.sort(function(a, b){return a - b}); // --> 3, 12, 23


If we want to sort the numbers in descending order, this time we need to subtract the second parameter (b) from the first one (a):

const numbers = [3, 23, 12];

numbers.sort(function(a, b){return b - a}); // --> 23, 12, 3


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
 The push() method will add one or more arguments at the end of an array in JavaScript.
 
 ```javascript
 let arr = [0, 1, 2, 3];
arr.push(4);
console.log(arr); // [0, 1, 2, 3, 4]
```

The push() method also returns the new length of the array.

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

The pop() method removes the last element from an array and returns that element. This method changes the length of the array.

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
The shift() method removes the first element from an array and returns that removed element. This method changes the length of the array.

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
