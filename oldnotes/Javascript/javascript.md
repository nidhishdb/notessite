## Javascript

 <link
      rel="stylesheet"
      href="https://cdnjs.cloudflare.com/ajax/libs/animate.css/3.7.2/animate.min.css"
    />
<div class="animated fadeIn">

<img src="https://upload.wikimedia.org/wikipedia/commons/thumb/9/99/Unofficial_JavaScript_logo_2.svg/480px-Unofficial_JavaScript_logo_2.svg.png" alt="javascript logo" width=300 style="border-radius:4px">


>We are what we repeatedly do. Excellence, then, is not an act, but a habit. - *Aristotle*
- - - -
<link href="https://fonts.googleapis.com/css2?family=Montserrat&display=swap" rel="stylesheet">
<style>
a{color:#faedcb;background-color:#403d39;padding:4px;border-radius:3px;}
 body{background-color:#0c1821;color:#faedcb;line-height:2.0rem;font-size:1.0em;font-family:Montserrat}
 code{color:#eb5e28;}
 .vscode-light pre {
  background-color: rgba(32, 33, 36, 0.4);
  box-shadow: 0px 0px 2px 1px #00000070;
}
</style>
List of new JS features
https://github.com/daumann/ECMAScript-new-features-list

What are the two elements of a pure function?
1. Deterministic --> always produces the same results given the same inputs
2. No Side Effects -->  It does not depend on any state, or data, change during a program’s execution. It must only depend on its input elements.

#### Promises
Promises are the ideal choice for handling asynchronous operations in the simplest manner. They can handle multiple asynchronous operations easily.

Syntax:
```js
var promise = new Promise(function(resolve, reject){
     //do something
});
```

Promise constructor takes only one argument,a callback function.
    
Callback function takes two arguments, resolve and reject
    
Perform operations inside the callback function and if everything went well then call resolve.

If desired operations do not go well then call reject.

A promise will start doing whatever task you give it as soon as the promise constructor is invoked.

```js
const promise = new Promise((resolve,reject)=>{
    if(true){
        resolve('done');
    }else{
        reject('error');
    }
})

const promise2 = new Promise((resolve,reject)=>{
    setTimeout(resolve,2000,'yeye')
})


const promise3 = new Promise((resolve,reject)=>{
    setTimeout(resolve,1000,'kek')
})

promise.then(res => console.log(res))
promise2.then(res => console.log(res))
promise3.then(res => console.log(res))

Promise.all([promise,promise2,promise3]).then(values => {console.log(values)})
```
Using `.then()` we can do something with resolved promise. 

`Promise.all()` is actually a promise that takes an array of promises as an input (an iterable). Then it gets resolved when all the promises get resolved or any one of them gets rejected.

`Promise.resolve()` and `Promise.reject()`

`Promise.resolve()` method in JS returns a Promise object that is resolved with a given value.
```js
const promise = Promise.resolve(
  setTimeout(() => {
    console.log("success");
  }, 4000)
);
```
The `Promise.reject()` method returns a Promise object that is rejected with a given reason.

```js 
Promise.reject('failed')
  .catch(console.log('Ooops something went wrong'))
```

`Async/Await` (Syntactic Sugar for Promises)


```js
function resolveAfter2Seconds() {
  return new Promise(resolve => {
    setTimeout(() => {
      resolve('resolved');
    }, 2000);
  });
}

async function asyncCall() {
  console.log('calling');
  const result = await resolveAfter2Seconds();
  console.log(result);
  // expected output: 'resolved'
}

asyncCall();
```
```js
async function f() {

  let promise = new Promise((resolve, reject) => {
    setTimeout(() => resolve("done!"), 1000)
  });

  let result = await promise; // wait until the promise resolves (*)

  alert(result); // "done!"
}

f();
```
The async keyword before a function has two effects:

   * Makes it always return a promise.
   * Allows await to be used in it.

The await keyword before a promise makes JavaScript wait until that promise settles, and then:

   * If it’s an error, the exception is generated. 
   * Otherwise, it returns the result.

We can use a `try...catch` block inside async functions to catch errors

#### JSON:Javascipt Object Notation
#### JSON.parse: JSON to Object
```js
var obj = JSON.parse('{"name":"John","age":30,"city":"New york"}')
```
#### JSON.stringify() : Object to JSON
```js
var myJSON = JSON.stringify(obj);
```

#### fetch()
The Fetch API provides an interface for fetching resources (including across the network)
```js
fetch(url,options) // Call the fetch function passing the url of the API as a parameter
.then(function() {
    // Your code for handling the data you get from the API
})
.catch(function() {
    // This is where you run code if the server returns any errors
});
```

#### `join()` method returns the array as a string.
The elements will be separated by a specified separator. The default separator is comma (,)



#### `for in` loop and `for of` loop:
We can iterate over Array items using `for of` loop:
```js
let fruits = ['apples','bananas','musumbi','pineapple'];

for (fruit of fruits){
    console.log(fruit);
}
/*
apples
bananas
musombi
pineapple
*/
```
We can iterate over Object properties (keys) using `for in` loop:
```js
const obj = {
    username0:123,
    username1:'piko',
    username2:321,
    username3:'hahhaha'
}
for (user in obj){
    console.log(user);
}
/*
username0
username1
username2
username3
*/
```
#### ES7:
`.includes()` method determines whether a string contains the characters of a specified string.

** exponent operator was added. 

#### ES8:
`.padStart()` - adds padding to the start of the string to make the total length of the string equal to the value provided in parameter.

`.padEnd()` - adds padding to the end of the string to make the total length of the string equal to the value provided in parameter.

#### ES10:
`.flat()` can convert nested arrays into simple array. It also removes empty slots in an array.

The depth of the nested array can be specified in it's parameters. By default it is 1.
```js
  let a = [1,2,,[22],34,[5,6]];
  console.log(a.flat()) //[ 1, 2, 22, 34, 5, 6 ]
```

`.flatMap()` - *combo of flat() and map()*

Is equivalent to doing a map followed by a flat with a depth of 1 separately.
```js
let names = ['john','sally',['joe'],['mama']];
let newNames = names.flatMap(name=> name + '!')
//[ "john!", "sally!", "joe!", "mama!" ]
```
`.trimStart()` is a string method that is used to remove whitespace characters from the start of a string. 

`.trimEnd()` is a string method that is used to remove whitespace characters from the end of a string. 

**converting arrays into objects and objects into arrays:** `Object.fromEntries()` and `Object.entries()`

arrays into objects: `Object.fromEntries()`
```js
userProfiles = [['Tom',19],['Benjamin',18],['Kevin',18],['Ryan',19]];
Object.fromEntries(userProfiles); 
//this is the opposite of Object.entries() which gives back array from object
```
objects into arrays: `Object.entries()`
```js
let obj = {a:1,b:2,c:3}
Object.entries(obj);
```

#### let and const
`let` and `const` are block scoped whereas `var` is function scoped.

#### copying arrays and objects 
Array: Pass by **reference** copy:
```js
let a = [1,2,3,4];
let b = a;
b.push(5);
console.log(b); //[ 1, 2, 3, 4, 5 ]
console.log(a); // [ 1, 2, 3, 4, 5 ]
```
Array: Pass by **value** copy:
```js
let a = [1,2,3,4];
let b = [].concat(a);
b.push(5);
console.log(b); //[ 1, 2, 3, 4, 5 ]
console.log(a); //[ 1, 2, 3, 4 ]
```

Objects: Pass by **reference** copy:
```js
let a = {
    a:'a',
    b:'b',
    c:'c'
}
let b = a;
b.d = 'd';
console.log(a); // { a: 'a', b: 'b', c: 'c', d: 'd' }
console.log(b); // { a: 'a', b: 'b', c: 'c', d: 'd' }
```
Objects: Pass by **value** copy:
```js
/*Note: This only does a shallow copy,see below for deep clone (copying nested objects)*/
let a = {
    a:'a',
    b:'b',
    c:'c'
}
let b = Object.assign({},a)
b.d = 'd';
console.log(a); // { a: 'a', b: 'b', c: 'c' }
console.log(b); // { a: 'a', b: 'b', c: 'c', d: 'd' }

// or using spread operator, works the same way

let c = {...a}
c.d = 'd';
console.log(a); //{ a: 'a', b: 'b', c: 'c' }
console.log(c); //{ a: 'a', b: 'b', c: 'c', d: 'd' }
```
```js
//Deep clone (copying nested objects by value)
let a = {
    a:1,
    b:2,
    c:3,
    d:{deep:'try and copy me'}
};
let deepClone = JSON.parse(JSON.stringify(a));
a.d = 'hahaha';
console.log(a); //{ a: 1, b: 2, c: 3, d: 'hahaha' }
console.log(deepClone); //{ a: 1, b: 2, c: 3, d: { deep: 'try and copy me' } }
```
#### Type Coercion

https://dorey.github.io/JavaScript-Equality-Table/
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Equality_comparisons_and_sameness

good stuff to read when you can't fall asleep,this is proven to cure insomia

https://www.ecma-international.org/ecma-262/5.1/#sec-11.9.3

#### Destructuring
The destructuring syntax makes it possible to unpack values from arrays, or properties from objects, into variables.

```javascript
const obj = {
  name:"Halie",
  age:18
}
const { name, age } = obj;
```

### Arrays

```javascript
//Arrays
//create:
const games = ['batman',2012,'assassins creed'];
console.log(games[1]);
//modify:
games[0] = 'dark knight';
//Arrays declared with an const cannot be reassigned but can be modified

//common array methods:
//.push() allows us to add items to the end of an array
//.pop(), removes the last item of an array.
//shift() method removes the first element from an array and returns that removed element. 
//The unshift() method adds one or more elements to the beginning of an array and returns the new length of the array.
//The slice() method returns a shallow copy of a portion of an array into a new array object selected from begin to end (end not included). The original array will not be modified.
//The indexOf() method returns the first index at which a given element can be found in the array, or -1 if it is not present.
```

#### Array Methods:
https://sdras.github.io/array-explorer/ -find array methods without digging through the docs

[W3C Array Methods](https://www.w3schools.com/jsref/jsref_obj_array.asp)

The `.forEach()` method calls a function once for each element in an array, in order.

The `.map()` method **creates a new array** with the results of calling a function for every array element.

The `.filter()` method creates an array filled with all array **elements that pass a test/condition** (provided as a function).

The `reduce()` method executes a reducer function (that you provide) on each element of the array, resulting in a single output value.

```js
const array = [1,2,10,16];
const reduceArray = array.reduce((accumulator,num)=>{
  return accumulator + num;
},1)

console.log(reduceArray); // 30
```

Your reducer function's returned value is assigned to the accumulator, whose value is remembered across each iteration throughout the array and ultimately becomes the final, single resulting value.

We can specify the initial value of the accumulator in the function's second parameter.

#### DOM Manipulation

#### cheatsheet:
DOM Selectors
--------------
getElementsByTagName<br>
getElementsByClassName<br>
getElementById

querySelector<br>
querySelectorAll

getAttribute<br>
setAttribute

##Changing Styles<br>
style.{property} //ok

className //best<br>
classList //best

classList.add<br>
classList.remove<br>
classList.toggle

##Bonus<br>
innerHTML //DANGEROUS

parentElement<br>
children

It is important to CACHE selectors in variables
#### Events:
https://developer.mozilla.org/en-US/docs/Web/Events

#### Add an Event:

`element.addEventListener("eventhere",functionhere)`

#### create element:
`document.createElement('element');`

#### create TextNode:
`document.createTextNode("Hello World");`

#### appendChild()
The `.appendChild()` method appends a node as the last child of a node.

Tip: If you want to create a new paragraph, with text, remember to create the text as a Text node which you append to the paragraph, then append the paragraph to the document.

#### event.target:
The target event property returns the 'element' that triggered the event.


#### Closures: 
In JavaScript, if you declare a function within another function, then the local variables of the outer function can remain accessible to inner function after returning from it.

* When a function (foo) declares other functions (bar and baz), the family of local variables created in foo is not destroyed when the function exits. The variables merely become invisible to the outside world. foo can therefore cunningly return the functions bar and baz, and they can continue to read, write and communicate with each other through this closed-off family of variables ("the closure") that nobody else can meddle with, not even someone who calls foo again in future.

##### example 1:
```javascript
function a(){           //parent function
    var name = 'nidhish';
    function b(){// child function referencing parent function's local variable
      console.log(name);
    }
    return b;    // exit a() function after returning the b function
}

var c = a();                
c();  //c() still remembers variable 'name'
```


This example shows that the local variables are not copied — they are kept by reference. It is as though the stack-frame stays alive in memory even after the outer function exits!
```javascript
function a(){
    var num = 10;
    function b(){
        console.log(num);
    }
    num++;
    return b;
}

var c = a();
console.log(c)
c();
```
##### example 2:
```javascript
function sayHello2(name) {
  var text = 'Hello ' + name; // Local variable
  var say = function() { console.log(text); }
  return say;
}
var say2 = sayHello2('Bob');
say2(); // logs "Hello Bob"
```

#### Currying: 
When a function, instead of taking all arguments at one time, takes the first one and return a new function that takes the second one and returns a new function which takes the third one, and so forth, until all arguments have been fulfilled.

The arguments are kept "alive"(via closure) and all are used in execution when the final function in the currying chain is returned and executed.

```javascript
const multiply = (a,b) => a*b; //this function can be curried as:

const curriedMultiply = (a) => (b) => a*b;

curriedMultiply(2)(3) // 6 , here we're passing arguements to both functions at once

const multiplyBy5 = curriedMultiply(5); //now we have a function which multiplies any number by 5
multiplyBy5(5); // 25
multiplyBy5(10); // 50
multiplyBy5(11); // 55
```

#### function compositon/compose:
Function composition is a mechanism of combining multiple simple functions to build a more complicated one. The result of each function is passed to the next one. 
```javascript
const compose = (f,g) => (a) => f(g(a));

const add = (num) => num + 1;

compose(add,add)(5); // 7
```

```javascript
const greetMe = (a,b,c) => (d) => a(b(c(d)));

const a = (d) => d + "!";

const b = (d) => d + " ,Good Morning";

const c = (d) => "Hi! " + d;
console.log(greetMe(a,b,c)("Nidhish")); //Hi! Nidhish ,Good Morning!


```

#### Callback functions:
A callback function is a function that is passed as an argument to another function, to be “called back” at a later time. A function that accepts other functions as arguments is called a higher-order function, which contains the logic for when the callback function gets executed. It’s the combination of these two that allow us to extend our functionality.

To illustrate callbacks, let’s start with a simple example:
```javascript
function createQuote(quote, callback){ 
  var myQuote = "Like I always say, " + quote;
  callback(myQuote); // 2
}

function logQuote(quote){
  console.log(quote);
}

createQuote("eat your vegetables!", logQuote); // 1

// Result in console: 
// Like I always say, eat your vegetables!
```

Notice that we are not appending parentheses to logQuote when we pass it in as an argument. This is because we do not want to execute our callback function right away, we simply want to pass the function definition along to the higher-order function so that it can be executed later.

Additionally, we can pass in anonymous functions as callbacks. The below call to createQuote would have the same result as the above example:
```javascript
function createQuote(quote, functionToCall) { 
  var myQuote = "Like I always say, " + quote;
  functionToCall(myQuote);
}

createQuote("eat your vegetables!", function(quote){ 
  console.log(quote); 
});
```

#### 3 ways of declaring functions
#### Ist way:
```javascript
function greet(){
    console.log("Hi"); //function declaration
}
```

#### IInd way:
```javascript 
const hi = function(){
    console.log("Hi"); //function expression
};
```
#### IIIrd way:
```javascript 
//Arrow functions with no arguements
const greet1 = () => {console.log("Hi")};
```
```javascript
//with 1 arguement
const hi2 = "Hi";
const greet2 = hi => {console.log(hi)};
```
```javascript
//with 2 or more arguements 
const hello = "Hello";
const greet3 = (hi,hello) => {console.log(`${hi} ${hello}`)};
```
```javascript
//single line arrow function 
const greet4 = hi => hi; // returns hi
```
#### Objects 
https://sdras.github.io/object-explorer/ - find object methods without digging through the docs
```javascript
const spaceship = {
    'Fuel Type': 'Turbo Fuel',
    'Active Duty': true,
    homePlanet: 'Earth',
    numCrew:5
};
//can be accessed with . or []
//with . eg:
console.log(spaceship.homePlanet);
//with [] eg:
console.log(spaceship['Fuel Type']);
```
Iterating over objects:
```js
const obj = {
    username0:123,
    username1:'piko',
    username2:321,
    username3:'hahhaha'
}
//Object.keys(obj) – returns an array of keys.
Object.keys(obj).forEach((key,index)=>{
    console.log(`${key}:${obj[key]}`)
})

// ES8 Method:

//Object.values(obj) – returns an array of values.
Object.values(obj).forEach(value => {console.log(value)}) 

//Object.entries(obj) – returns an array of [key, value] pairs.
Object.entries(obj).forEach(([key,value])=>{console.log(`${key}:${value}`)})

Object.entries(obj).forEach((entry)=>console.log(`${entry[0]}:${entry[1]}`))
```

```javascript
//we can write a function to get value of object like so
let returnAnyProp = (objectName, propName) => objectName[propName];

console.log(returnAnyProp(spaceship, 'homePlanet')); // Returns 'Earth' which is outputted by console.log
```
```javascript
/*we can add,modify or delete properties to objects with . or []  Eg:*/
spaceship.type = 'alien';
/*but if the object is declared with a const then we can't reassign them but we
can still mutate them*/
//Eg:
spaceship = {captain: 'hashelse'} // shows error as no reassign allowed on const but we can still do this...
spaceship.captain = 'hashelse';
//we can delete with delete operator Eg:
delete spaceship.captain;

```
#### Methods:
```javascript
//Methods are nothing but functions in objects. Eg:
const alienShip = {
    invade: function(){
        console.log("Charging Lasers...")
    }
};
//with ES6 we can write the same as below:
const alienShipES6 = {
    invade () {
        console.log("Charging Lasers...")
    }
};
//calling methods Eg:
alienShipES6.invade();
```
```javascript
//Nested Objects
const superSpaceship = {
     telescope: {
        yearBuilt: 2018,
        model: '91031-XLT',
        focalLength: 2032
     },
    crew: {
        captain: {
            name: 'Sandra',
            degree: 'Computer Engineering',
            encourageTeam() { console.log('We got this!') }
         }
    },
    engine: {
        model: 'Nimbus2000'
     },
     nanoelectronics: {
         computer: {
            terabytes: 100,
            monitors: 'HD'
         },
        'back-up': {
           battery: 'Lithium',
           terabytes: 50
         }
    }
};
// Accessing them
superSpaceship.nanoelectronics['back-up'].battery; // Returns 'Lithium'
```
```javascript
//functions can change object properties,they actually mutate the object permanently (even when the object is assigned to a const variable). 
const spaceship2 = {
  homePlanet : 'Earth',
  color : 'silver'
};

let paintIt = obj => {
  obj.color = 'glorious gold'
};

paintIt(spaceship2);

spaceship2.color // Returns 'glorious gold'
```

```javascript
//However, reassignment of the spaceship variable wouldn't work in the same way: 
let spaceship3 = {
  homePlanet : 'Earth',
  color : 'red'
};
let tryReassignment = obj => {
  obj = {
    identified : false, 
    'transport type' : 'flying'
  }
  console.log(obj) // Prints {'identified': false, 'transport type': 'flying'}

};
tryReassignment(spaceship3) // The attempt at reassignment does not work.

spaceship3 // Still returns {homePlanet : 'Earth', color : 'red'};

spaceship3 = {
  identified : false, 
  'transport type': 'flying'
}; // Regular reassignment still works.


/*This Happens because
When we passed spaceship3 into that function, obj became a reference to the memory location of the spaceship3 object, but not to the spaceship3 variable. This is because the obj parameter of the tryReassignment() function is a variable in its own right. The body of tryReassignment() has no knowledge of the spaceship3 variable at all!*/
```

```javascript
//Looping through objects with for...in
//Eg:
let spaceship4 = {
    crew: {
    captain: { 
        name: 'Lily', 
        degree: 'Computer Engineering', 
        cheerTeam() { console.log('You got this!') } 
        },
    'chief officer': { 
        name: 'Dan', 
        degree: 'Aerospace Engineering', 
        agree() { console.log('I agree, captain!') } 
        },
    medic: { 
        name: 'Clementine', 
        degree: 'Physics', 
        announce() { console.log(`Jets on!`) } },
    translator: {
        name: 'Shauna', 
        degree: 'Conservation Science', 
        powerFuel() { console.log('The tank is full!') } 
        }
    }
}; 
// for...in
for (let crewMember in spaceship4.crew) {
  console.log(`${crewMember}: ${spaceship4.crew[crewMember].name}`)
};

/* Output:

captain: Lily
chief officer: Dan
medic: Clementine
translator: Shauna
*/
```
```javascript
//accessing another property within a property of the same object (using the
//this keyword) Eg:
const goat = {
  dietType: 'herbivore',
  makeSound() {
    console.log('baaa');
  },
  diet() {
    console.log(this.dietType);
  }
};

goat.diet(); 
// Output: herbivore
//which is same as 
const goat2 = {
  dietType: 'herbivore',
  makeSound() {
    console.log('baaa');
  },
  diet() {
    console.log(goat2.dietType); // this is replaced with the calling object which is the goat, meaning this keyword is a nothing but a reference to the calling object
  }
};

goat2.diet();
// Output: herbivore
```
#### Getters:
```javascript
// AVOID USING ARROW FUNCTIONS IN AN OBJECT WHEN USING THE 'this' KEYWORD IN AN
// METHOD,STUPID JAVASCRIPT!

// by convention don't modify properties beginning with an _ (underscore) 
// Eg:
 const bankAccount = {
  _amount: 1000
}
bankAccount._amount = 1000000; // you 'can' modify but you 'should'nt'. It's a convention
// the proper way to modify the amount property would be to use a 'getter' function.
// Eg of a getter function:
const person = {
  _firstName: 'John',
  _lastName: 'Doe',
  get fullName() {
    if (this._firstName && this._lastName){
      return `${this._firstName} ${this._lastName}`;
    } else {
      return 'Missing a first name or a last name.';
    }
  }
}

// To call the getter method: 
person.fullName; // 'John Doe'

//Getters can perform an action on the data when getting a property.
//Getters can return different values using conditionals.
//In a getter, we can access the properties of the calling object using this
//
//Another thing to keep in mind when using getter (and setter) methods is that properties cannot share the same name as the getter/setter function. If we do so, then calling the method will result in an infinite call stack error. One workaround is to add an underscore before the property name like we did in the example above.
```
#### Setters:
```javascript
//Setters can be used to reassign values of existing properties within an object.Eg:
const person2 = {
  _age: 37,
  set age(newAge){
    if (typeof newAge === 'number'){
      this._age = newAge;
    } else {
      console.log('You must assign a number to age');
    }
  }
};
//then to use the setter method:
person2.age = 40;
console.log(person2._age); // Logs: 40
person2.age = '40'; // Logs: You must assign a number to age

/*Like getter methods, there are similar advantages to using setter methods that include checking input, performing actions on properties, and displaying a clear intention for how the object is supposed to be used. Nonetheless, even with a setter method, it is still possible to directly reassign properties. For example, in the example above, we can still set ._age directly:
*/
person2._age = 'forty-five'
console.log(person2._age); // Prints forty-five
```
#### Dynamic Object Properties:
```javascript
const name = "John";
const obj = {
  [name]: 'Wick',
  [1+2]:'Hihi'
}
console.log(obj); // { '3': 'Hihi', John: 'Wick' }
```

#### Factory Functions

```javascript
//A factory function is a function that returns an object and can be reused to make multiple object instances.
const monsterFactory = (name, age, energySource, catchPhrase) => {
  return { 
    name: name,
    age: age, 
    energySource: energySource,
    scare() {
      console.log(catchPhrase);
    } 
  }
};
/*To make an object that represents a specific monster like a ghost, we can call monsterFactory with the necessary arguments and assign the return value to a variable:*/

const ghost = monsterFactory('Ghouly', 251, 'ectoplasm', 'BOO!');
ghost.scare(); // 'BOO!'

//We can do the same with ES6 Destructuring (assigning arguements to variables)
//as follow:
//
//
const monsterFactory2 = (name, age, energySource, catchPhrase) => {
  return { 
    name,
    age, 
    energySource,
    scare() {
      console.log(catchPhrase);
    } 
  }
};
```
```javascript
//Assigning object properties to variables ,Eg:
const vampire = {
  name: 'Dracula',
  residence: 'Transylvania',
  preferences: {
    day: 'stay inside',
    night: 'satisfy appetite'
  }
};
const residence = vampire.residence;
console.log(residence); // Prints 'Transylvania'

//using destructured assignment :
const { residence } = vampire; 
console.log(residence); // Prints 'Transylvania'
const { day } = vampire.preferences; 
console.log(day); // Prints 'stay inside'
```
#### Classes
```javascript
class Giraffe {
  constructor(name) {
    this._name = name;
    this._behavior = 0;
  }

  get name() {
    return this._name;
  }

  get behavior() {
    return this._behavior;
  }

  incrementBehavior() {
    this._behavior++;
  }
}
//notice although looking similar to Objects you cannot put commas between
//methods
//
//create a new instance of the class
const halley = new Giraffe('Halley');
```
#### Inheritence
```javascript
//Parent Class
class Animal {
  constructor(name) {
    this._name = name;
    this._behavior = 0;
  }

  get name() {
    return this._name;
  }

  get behavior() {
    return this._behavior;
  }   

  incrementBehavior() {
    this._behavior++;
  }
}

//child class
class Dog extends Animal {
  constructor(name) {
    super(name);
  }
}

//child class with _usesLitter as additional property
class Cat extends Animal {
  constructor(name, usesLitter) {
    super(name);
    this._usesLitter = usesLitter;
  }

  get usesLitter() {
    return this._usesLitter;
  }
}
```
#### Static Class
```javascript
//Sometimes you want to call methods directly from the class, but not from an instance of the class.
//
class Animal2 {
  constructor(name) {
    this._name = name;
    this._behavior = 0;
  }

  static generateName() {
    const names = ['Angel', 'Spike', 'Buffy', 'Willow', 'Tara'];
    const randomNumber = Math.floor(Math.random()*5);
    return names[randomNumber];
  }
}
console.log(Animal2.generateName()); // returns a name
```







































