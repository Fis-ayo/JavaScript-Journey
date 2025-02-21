# JAVASCRIPT BREAKDOWN
It is advisable to have knowledge of a programming language, especially **Python**, before using this to learn the basics of Javascript. If you're new to JavaScript, fret not this is for you.

## Comments
// in-line comment
/* this is a
 multi-line comment */

## Data Types and variables
Variable names and functions in JavaScript are case sensitive.
 1. __undefined:__ used when a variable has not really been defined.
 2. __null__, __boolean__, __string__, 
 3. __symbol:__ immutable primitive value that is unique.
 4. __number__
 5. __object:__ store key value pairs

 ## Declaring a variable
 1. __var:__ Variables declared using this can be used anywhere.
 2. __let:__ can only be used in the scope/block it is declared. Variables cannot be declared twice.
 3. __const__ variables are always constant.
 ### LET VS VAR
 _let_ does not allow to declare a variable twice, while _var_ does. It is advisable to use let as much as possible because was created recently and it fixes some quirks that var has. Throughout this lesson, we'll be using _var_ and this challenge I have for you is to try each code and trying to replace _var_ with _let_ and see how it can be used.
 ```js
 function variableCompare(){

    let i = 20;
    if (i<23){
        let i = 30
        console.log(i);

    }
 }
console.log(i);


/*OUTPUT
30
20 */
```

 ```js
/*The following code gives an error*/
function variableCompare(){
    if (true){
        let i = 20
        console.log(i);
    }
    console.log(i); // You get an error indication that i wasn't defined.
}
variableCompare();
 ```



 ## Operators
 ### Arithmetic Operators
 - __%__ : Modulus
 - __*__ : Multiplication
 - **/** : Division
 - **+** : Addition
 - **-** : Subtraction
 - **++** : Increment
 - **--** : Decrement
 ### Assignment Operator
 - __=__ : Assignment
 - **+=, -=, *=, /=** : Operators and equal to
### Relational Operators
 - == : Equality. Doesn't check the data type. `3=="3"` returns true.
 - === : Strict Equality operator. Checks the data type. `3==="3"` returns false.
 - != : Inequality
 - !== : Strict inequality
 - __>,<, >=, <=__: Greater than, Lesser than, Greater or equal to, Less than or equal to.
 ### Logical Operators
 - && : AND
 - || : OR


---
console.log() allows to print things in the console. 
`console.log("Hello JavaScript);`

 ## Strings
 Strings are declared in quotation marks. The second line helps to escape quotations within a string. Strings are immutable meaning the individual characters cannot be manipulated; you can only change the string in the variable.
 ```js
  var myStr = "Learning";
  myStr = "I am a \"double quoted\" individual!";
  myStr = `'I am a "double quoted" String'`;
```
__Concatenate__ strings using the *Plus(+)* operator. A string variable can also be concatenated.
```js
    var name = "Sarah";
    var ourStr = "Hi! My name is " + name + "; what is yours?";
```
**Length** of a string can be found by using the *.lenght* keyword after the string variable e.g `ourStr.length`.<br>
**Bracket Notation** is used to get any character/letter from a string e.g `ourStr[0]` would give `H`.
### Escape Squences in Strings
 - \\': single quote
 - \\": double quote
 - \\\: backslash
 - \n: newline
 - \r: carriage return
 - \t: tab
 - \b: backspace
 - \f: form feed

 ### Template literals
 Are used to make complex strings easier. For instance, 
 ```js
 const person = {
    name: "Dan",
    age: 24;
 }

 const greeting  = `Hello, my name is ${person.name}!
 I am ${person.age} years old.`

 console.log(greeting);

 /*OUTPUT
 Hello, my name is Dan! I am 24 years old.
 */
 ```
 

## Arrays
Arrays allow you to store several pieces of data in one place. Every element has to be separated with a comma.
1. Single Array
    ```js
    var array = ["John", 67];
    ```
2. Double/Nested Array
    ```js
    var doubleArray = [["Dimel", 25], ["John", 67]]
    ```
**Access single array data using indexes** by using the bracket notation `array[1]`. Unlike strings, arrays are mutable. You can access an index/position in the array and change it's value e.g `array[0] = 34`.<br>
**Access double array data using indexes** by using double bracket notation `doubleArray[0][0]`. The number of times an array is nested determines how many bracket notation can be used to access each data.

### Manipulating Arrays
- **Push():** This function is used to append data to the end of an array. 
    ```js
    var myArray = ["John", 34, 56, 67];
    myArray.push(["Sahid", 23]);
    console.log(myArray)
    ```
    ```OUTPUT
    ["John", 34, 56, 67, ["Sahid", 23] ]
    ```
- **Pop():** The pop() function removes the last element from an array e.g `myArray.pop()` returns `["Sahid", 23]`.
- **Shift():** The shift() function removes the first element from the array and returns it. `myArray.shift()`.
- **Unshift():** The unshift() function is similar to the push(). Instead of adding elements to the the end of the array, unshift() adds elements to the beginning of the array.
    ```js
    var ourArray = ["John", 34, 56, 67];
    ourArray.unshift("Peter");
    console.log(ourArray)
    ```
    ```OUTPUT
    ["Peter", "John", 34, 56, 67]
    ```

## Functions
Functions allow for code reusability, promoting modularity and better organization. They help break down complex tasks into smaller, manageable parts, improving readability and maintainability.
```js
function myFunction(n, m) //Can take in parameters and be passed in the function call (arguments).
{
console.log("Learning JavaScript?");
console.log(n+m);
}
myFunction(5, 6); //Function call with Arguments
```
```OUTPUT
    Learning JavaScript?
    11
```
**Global Scope** refers to the visibility of variables. Global scope variable are variables that can be seen anywhere in your JavaScript code. **Local Scope** are variables that are declared within the function.
It is possible to have both a global and local scope of the same variable name. However, the local scope takes precedence. <br>


### Return a value from a function with the `return` statement.
```js
    var name = "T-Shirt"; // Global scope
    function wear(){
    var name = "sweater"; // Local Scope
    return name;
    }
    name = wear();
    console.log(name);
```
## Queue
A queue is an abstract data structure where items are kept in order. Items can be added to the back of the queue and only taken from the front of the queue following the FIFO (First In First Out) rule.
```js
function queue(arr, item){
    arr.push(item);
    return arr.shift();
}
var fullArr = [1,2,3,4,5];

//JSON.stringify changes an array to a string. It changes the way it is printed out.

console.log("Before: " + JSON.stringify(fullArr)); 
console.log(nextInLine(fullArr, 6));
console.log("After: " + JSON.stringify(fullArr));
```
```OUTPUT
Before: [1,2,3,4,5]
1
After: [2,3,4,5,6]
```

## Boolean Values
A data type that holds only two values __true__ and __false__. `return 10<15` outputs `true`.

### Conditional Logics 
### If Statements
We can also add the comparison operators to the examples.
```js
function bools(check){
    if(check){
        return "Yes it is true"; 
    }
    return "No it is false";
}

console.log(bools(false));
console.log(bools(3=='3')); //Equality operator
console.log(bools(3==='3')) //Strict equality operator
console.log(bools(3===3))
```
```OUTPUT
No it is false
Yes it is true
No it is false
Yes it is true
```

### Else Statements
```js
function bools(val){
    if(val<=8){
        return "Number is less"; 
    }else{
    return "Number is greater";
    }
}

console.log(bools(9));
```
**Else if statements** is used when you have multiple conditions that need to be addressed. Order matters when using these conditions
### Switch statements
```js
switch(value){
    case 1:
        //statement
        break;
    case 2:
        //statement
        break;
    case 3:
        //statement
        break;
    default:
        //statment
        break;
}
```

## JavaScript Objects
Objects are quite similar to arrays, but instead of data, you use properties. It is an easy way to store flexible data like *string*, *arrays*, *numbers*, and other objects. You ccan say it is similar dictionaries in python
```js
// "properties": value OR "key":"value" in Python
var ourDog={
    "name": "Camper",
    "legs": 4,
    "tails": 1
    "main class": "mammals"
};
```
Object properties can be accessed using Dot Notation. `ourDog.legs`. Bracket Notation also works if the properties have a space in it `ourDog['main class']`. They can be either used to change the value stored in a property or used to return the values. <br>
Add new properities by using the notations with a new property and name. `ourDog.hobbies = 5`<br>
Delete properties by using the `delete` keyword. `delete ourDog.legs`.<br>
Check if an object has a property by using the __hasOwnProperty__ method. `ourDog.hasOwnProperty(name)` and it returns true or false.<br><br>
**Complex/Multiple objects** can be stored in an array. 
```js
var animals=[
    ourDog={
        "name": "Camper",
        "legs": 4,
        "tails": 1
        "main class": "mammals"
    },
    ourCat={
        "name": "Quincy",
        "legs": 4,
        "tails": 2
        "main class": "entitled"
    }
];
```
<br>

**Nested Objects**

```js
var myStorage={
    "car":{
        "inside": {
            "glove box": "maps",
            "passenger seat": "crumbs"
        },
        "outside": {
            "trunk": "jack"
        }
    }
};

var accessing = myStorage.car.inside["glove box"];

console.log(accessing);
```
```
maps
```

## Loops
Loops allow you to run the same codes multiple times.
### While Loops
While loops run while a specific condition is true and stops when it's not.
```js
var myArray = [];
var i=0;

while(i < 5){
    myArray.push(i);
    i++;
}

console.log(myArray);
```
### Do...While Loops
A do...while loop always run at least one time then it would check the condition.
```js
var myArray = [];
var i=0;

do {
    myArray.push(i);
    i++;
}while(i < 5);

console.log(myArray);
```

### For Loops
A for loop is the most common type of loop in JavaScript.
```js
var myArray = [];

//for(initialization; condition; increment/decrement)

for(var i = 1; i < 6; i++){
    myArray.push(i);
}

console.log(myArray);
```
```
[1, 2, 3, 4, 5]
```
It can also be used to iterate through an _Array_.
```js
var myArray = [1, 2, 3, 4, 5];
var sum = 0;

for(var i = 0; i < myArray.length; i++){
    console.log(myArray[i]);
    sum+=myArray[i];
}

console.log(sum)
```
```
9
10
11
12
42
```
**Nested For Loops** can be accessed using nested for loops. This function accesses each data in the nested for loop and prints it out.
```js
var arr = [[1,2],[3,4],[5,6,7]];

for (var i=0; i<arr.length; i++){
    for (var j=0; i<arr[i].length; j++){
        console.log(arr[i][j]);
    }
}
```
### Coding challenge
Create a Profile Lookup
```js
var contacts =[
    {
        "firstname": "Akira",
        "lastName": "Laine",
        "number": "0543323424",
        "likes": ["Pizza", "Coding", "Brownie Points"]
    },
    {
        "firstname": "Harry",
        "lastName": "Potter",
        "number": "03456368928",
        "likes": ["Hogwarts", "Magic", "Hagrid"]
    },
    {
        "firstname": "Sherlock",
        "lastName": "Holmes",
        "number": "048735647",
        "likes": ["Intriguing Cases", "Violin"]
    },
    {
        "firstname": "Kristian",
        "lastName": "Vos",
        "number": "unknown",
        "likes": ["JavaScript", "Gaming", "Foxes"]
    }
];

function lookUpProfile(name, prop){
    for (var i=0; i<contacts.length; i++){
        if (contacts[i].firstname === name){
            return contacts[i][prop] || "No such property"; //The || (or) operator is similar to or in python.
        }
    }


    return "Name does not exist!"

}

var data = lookUpProfile("Sherlock", "lastName");
console.log(data);
```
```
Holmes
```

## Useful Functions
### Random Function
__Fractions__ can be generated using the `Math.random()` function. Numbers are between 0 (inclusive) & 1 (exclusive).
__Whole Numbers__ can be generated using `Math.floor()` function, which rounds down to the nearest whole number. For instance, `Math.floor(Math.random() * 10)` generates a number between 0 & 9.

#### Let's create a program that generates random numbers within a range.
```js
function randomrange(min, max){
    return Math.floor(Math.random() * (max-min+1))+min;
}

console.log(randomrange(1, 9));
```
### ParseInt Function
It takes a string and returns an integer. If it cannot be converted, it returns _NAN_ for Not A Number. `parseInt("56");` Also, it can be used with a Radix (Number bases). `str = "111"; parseInt(str, 2)`. It passes it as base 2 and not defualt base 10.

### Conditional Ternary Operator
It can be used to create a one line if-else expression.
```js
// condition ? statement-if-true : statement-if-false;

function checker(x, y){
    firstAns = x !== y ? "Yes" : "No";

    // Multi / Nested Conditional Ternary Operator
    secondAns = x < 0 ? "negative" : x > 0 ? "positive" : "zero";

    return firstAns, secondAns;
}

console.log(checker(-3, 6))
```
### Arrow Functions
Arrow function can be used to write concise anonymous functions. It allows you create shorter forms of functions by avoiding the __function__ and __return__ keywords. Moreover, it is best used when a function takes another function as an argument.
```js
//Original
var magic = function(){
    return new Date;
}

//Arrow function 
var magic = () => {
    return new Date();
}

/* OR a shorter versioncan*/
const magic = () => new Date();
```
**A function that concatenates arrays**
```js
    var addArr = (ar1, ar2) => arr1.concat()

    console.log(addArr([1,2,3], [4,5,6]))
```

### Higher Order Arrow Functions
```js
const realNumArray = [4, ,5.6, -9.8, 3.14, 14, 42, 6, 8.34, -2];

const squareList = (arr) => {
    // x means for every element in the array and the same goes for num. 
    const squaredIntegers = arr.filter(num => Number.isInteger(num) && num>0).map(x => x**2);
    return squaredIntegers;
}

const squaredIntegers = squareList(realNumArray);
console.log(squaredIntegers);
```

### Rest Operator with Function Parameters
The rest operators allows you to create a function that takes a variable number of arguments. Operator: `...` (3 dots). It can take in as many arguments.
```js
const sum = (function(){
    return function sum(....args){
        return args.reduce((a, b) => a+b, 0);
    };
})();

console.log(sum(1, 2, 3));

/*OUTPUT
6
*/
```

### Spread Operator
The spread operator syntax is similar to the the rest operator, but the spread operator is used to expand an array. For instance, `arr2 = arr1` makes _arr1_ and _arr2_ equal, so if you manipulate _arr1_, _arr2_ changes. However, `arr2 = [...arr1]` spreads out the content of _arr1_ into _arr2_.

## Destructuring Assignment
A special syntax for neatly assigning values taken from an object to a variable.
- **Example 1**
    ```js
    //Old Version
    var vowels = {x: 2, y: 4, z: 8};
    var a = vowel.x;
    var b = vowel.y;
    var c = vowel.z;

    // Destructuring
    const {x : a, y : b, z : c}= vowel; // a=2, b=4, c=8

    ```
- **Example 2**
    ```js
    const AVG_TEMPERATURES = {
        today : -5,
        tomorrow :  -9
    };

    function getTmrwTemp(avg_temp){

        const { tomorrow : tmrwTemp} = avg_temp;
        return tmrwTemp;
    }
    console.log(getTmrwTemp(AVG_TEMPERATURES));

    /*
    -9
    */
    ```
- **Example 3**
    Destructuring nested objects.
    ```js
    const AVG_TEMPERATURES = {
        today : {min : -9, max : -4},
        tomorrow : {min : -11, max : -2}
    };

    function getTmrwTemp(avg_temp){

        const { tomorrow : { max: tmrwTemp} } = avg_temp;
        return tmrwTemp;
    }
    console.log(getTmrwTemp(AVG_TEMPERATURES));

    /*
    -2
    */
    ```
- **Example 4**
    Destructuring from an array. The array on the left containing the variables can be used to access those numbers. The aim is to also get 4, so a space is left to simulate the actual position of where 4 is.
    ```js
    const [z, x, , y] = [1, 2, 3, 4, 5, 6];
    console.log(z, x, y);
    ```
- **Example 5**
    Use it with the _rest_ operator. Aim: print an array without the first two elements.
    ```js
    const source = [1, 2, 3, 4, 5, 6, 7, 8, 9];
    function removeFirstTwo(list){
        const [ , , ...arr] = list; // ...arr stores the rest of the values in the array in the variable arr.
        return arr;
    }
    console.log(removeFirstTwo(source));
    console.log(source);

    /*OUTPUT
    [3, 4, 5, 6, 7, 8, 9]
    [1, 2, 3, 4, 5, 6, 7, 8, 9]
     */
    ```
- **Example 6**
    Use destructing for pass an object as an argument to a function. This is commonly used with API calls.
    ```js
    const stats = {
        max: 90,
        average: 80;
        middle: 50;
        min: 25;
    }

    const half = (function(){
        return function half({max, min}){
            return (max + min)/2.0;
        }
    })();
    console.log(stats);
    console.log(half(stats));
    ```

### Class syntax.
The class syntax is used to define a constructor function.
```js
function makeClass() {
    class Vegetable {
        constructor (name) {
            this.name = name;
        }
    }
    return Vegetable;
}
const Vegetable = makeClass();
const carrot = new Vegetable('carrot'); // Objects can be instantiated using the new keyword
console.log(carrot.name);
```
## Getter and Setters
If you are familiar with C++ or Java this should be quite easy for you. You can control the access to an object using getters and setters. This helps the use get and set the variables without directly accessing the private variables. E.g `_author` from the code below.
```js
class Book{
    constructor(author){
        this._author = author;
    }

    //getter
    getWriter(){
        return this._author;
    }

    //setter
    setWrite(upAuthor){
        this._author = upAuthor;
    }
}
```

## Import and Require
Importing a file or a function is very important expecially when working on a complex project. You use the _import_ keyword. 
`import {function_name} from "./file path"`. However, you have to use the _export_ functions and variables from one file, so that you can _import_ them in another file. Export a function `export {function_name};` and just use the _export_ keyboard with the variables you wish to export. <br>
Moreover, you can import everything from a file using __*__. `import * as anythingCreated from "file name";

## Reference
[Youtube](https://www.youtube.com/watch?v=PkZNo7MFNFg)


 
