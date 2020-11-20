# JAVASCRIPT-ALGORITHMS-AND-DATA-STRUCTURE-CERTIFICATION

## Solution to the problems of the JavaScript Algorithms and Data Structures Certifications of www.freecodecamp.org

# JAVASCRIPT - ALGORITHMS AND DATA STRUCTURE CERTIFICATION 

# ES6

## ES6: Use Destructuring Assignment to Assign Variables from Arrays

ES6 makes destructuring arrays as easy as destructuring objects.

One key difference between the spread operator and array destructuring is that the spread operator unpacks all contents of an array into a comma-separated list. Consequently, you cannot pick or choose which elements you want to assign to variables.

Destructuring an array lets us do exactly that:

```html
const [a, b] = [1, 2, 3, 4, 5, 6];
console.log(a, b); // 1, 2
```

The variable <code>a</code> is assigned the first value of the array, and <code>b</code> is assigned the second value of the array. We can also access the value at any index in an array with destructuring by using commas to reach the desired index:

```html
const [a, b,,, c] = [1, 2, 3, 4, 5, 6];
console.log(a, b, c); // 1, 2, 5
```

Use destructuring assignment to swap the values of <code>a</code> and <code>b</code> so that <code>a</code> receives the value stored in <code>b</code>, and <code>b</code> receives the value stored in <code>a</code>.

```html
let a = 8, b = 6;
// Only change code below this line
[a,b] = [b,a];
console.log(a,b);
```

## ES6: Use Destructuring Assignment with the Rest Parameter to Reassign Array Elements

In some situations involving array destructuring, we might want to collect the rest of the elements into a separate array.

The result is similar to ```html Array.prototype.slice()```, as shown below:

```html
const [a, b, ...arr] = [1, 2, 3, 4, 5, 7];
console.log(a, b); // 1, 2
console.log(arr); // [3, 4, 5, 7]
```

Variables <code>a</code> and <code>b</code> take the first and second values from the array. After that, because of the rest parameter's presence, <code>arr</code> gets the rest of the values in the form of an array. The rest element only works correctly as the last variable in the list. As in, you cannot use the rest parameter to catch a subarray that leaves out the last element of the original array.
_________________________________________________________________________________________________________________________________________________________________________________
Use destructuring assignment with the rest parameter to perform an effective ```html Array.prototype.slice()``` so that <code>arr</code> is a sub-array of the original array source with the first two elements omitted.

```html
const source = [1,2,3,4,5,6,7,8,9,10];
function removeFirstTwo(list) {
  "use strict";
  // Only change code below this line
  const [a,b, ...arr] = list; // Change this line
  // Only change code above this line
  return arr;
}
const arr = removeFirstTwo(source);
```


# INTERMEDIATE ALGORITHM SCRIPTING

## Intermediate Algorithm Scripting: Sum All Numbers in a RangePassed

We'll pass you an array of two numbers. Return the sum of those two numbers plus the sum of all the numbers between them. The lowest number will not always come first.

For example, <code>sumAll([4,1])</code> should return <code>10</code> because sum of all the numbers between 1 and 4 (both inclusive) is <code>10</code>.

```html
function sumAll(arr) {
  let max = Math.max(arr[0], arr[1]);
  let min = Math.min(arr[0], arr[1]);
  let sum = 0;
  for (let i = min; i <= max; i++){
    sum = sum + i;
  }
  return sum;
}

sumAll([1, 4]);
```

## Intermediate Algorithm Scripting: Diff Two Arrays

Compare two arrays and return a new array with any items only found in one of the two given arrays, but not both. In other words, return the symmetric difference of the two arrays.

## Note
You can return the array with its elements in any order.

```html
function diffArray(arr1, arr2) {
  var newArr = [];

  function onlyInone(firstarr, secondarr) {
    // Looping through an array to find elements that don't exist in another array
    for (var i = 0; i < firstarr.length; i++) {
      if (secondarr.indexOf(firstarr[i]) === -1) {
        // Pushing the elements unique to first to newArr
        newArr.push(firstarr[i]);
      }
    }
  }

  onlyInone(arr1, arr2);
  onlyInone(arr2, arr1);

  return newArr;
}

diffArray([1, 2, 3, 5], [1, 2, 3, 4, 5]);
```
                            
## Intermediate Algorithm Scripting: Seek and Destroy

You will be provided with an initial array (the first argument in the destroyer function), followed by one or more arguments. Remove all elements from the initial array that
are of the same value as these arguments.

## Note
You have to use the <code>arguments</code> object.

```html
function destroyer(arr) {
  var args = Array.prototype.slice.call(arguments);

  for (var i = 0; i < arr.length; i++) {
    for (var j = 0; j < args.length; j++) {
      if (arr[i] === args[j]) {
        delete arr[i];
      }
    }
  }
  return arr.filter(Boolean);
}
```

