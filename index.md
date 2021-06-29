1) Best Practices of Variable
In JavaScript, you can declare a variable using three keywords. These are var, const, and let. Now you might be thinking, “What is the difference between these keywords? These do the same thing which is declaring a variable.” No, they are not the same. Let’s see this example below…
// bad
var a = 1;
var b = 2;
// good
const a = 1;
const b = 2;
// good (But not in all cases)
let a = 1;
let b = 2;
In modern JavaScript, we don’t use var. Rather we use let and const. The only difference between let and const is, you can change the value of a variable which has declared using let but you can’t change the value of a variable which has declared using const.
2) Objects
Some developers use new keyword during the declaration of an object. You can easily differentiate between good practices and bad practices of Objects through this example…
// bad
const item = new Object();
// good
const item = {};
An Object in JavaScript shouldn’t be declared with new keyword.
3)Array
Some weird developers use new keyword during the declaration of an array. I don’t have any idea why they do that. You can easily differentiate between good practices and bad practices of Array through this example…
// bad
const items = new Array();
// good
const items = [];
An Array in JavaScript shouldn’t be declared with new keyword. Another bad practice that most developers do is the direct assignment to add items to an array. Let me show an example.
const someStack = [];
// bad
someStack[someStack.length] = 'abracadabra';
// good
someStack.push('abracadabra');
So from now, use push instead of direct assignment to add items to an array.
4) Destructuring
During destructuring, many developers do bad practices. Here are some examples of the difference between bad, good, and best practices of destructuring.
// bad
function getFullName(user) {
  const firstName = user.firstName;
  const lastName = user.lastName;
return `${firstName} ${lastName}`;
}
// good
function getFullName(user) {
  const { firstName, lastName } = user;
  return `${firstName} ${lastName}`;
}
// best
function getFullName({ firstName, lastName }) {
  return `${firstName} ${lastName}`;
}
During Array destructuring, you shouldn’t use the index number to destructure. Follow this example below.
const arr = [1, 2, 3, 4];
// bad
const first = arr[0];
const second = arr[1];
// good
const [first, second] = arr;
Here first and second is representing 1 and 2 in the array.
5) Strings
You should use single quotes '' for strings. Though using double quotes will not hamper your code. Here is an example of the best practices of strings…
// bad
const name = "Capt. Mugdho";
// bad - template literals should contain interpolation or newlines
const name = `Capt. Mugdho`;
// good
const name = 'Capt. Mugdho';
When you are programmatically making strings, use template string instead of quotes. Here is an example…
// bad
function sayHi(name) {
  return 'How are you, ' + name + '?';
}
// bad
function sayHi(name) {
  return ['How are you, ', name, '?'].join();
}
// bad
function sayHi(name) {
  return `How are you, ${ name }?`;
}
// good
function sayHi(name) {
  return `How are you, ${name}?`;
}
6) Arrow Functions
Use arrow function notation when you have to use an anonymous function. It will increase the readability of your code. An arrow function is recommended when you are declaring any type of function. Here is an example…
// bad
[1, 2, 3].map(function (x) {
  const y = x + 1;
  return x * y;
});
// good
[1, 2, 3].map((x) => {
  const y = x + 1;
  return x * y;
});
Arrow functions will help you to keep your code clean and more readable.
7) Modules
Many developers use the require keyword when he has to import a module. But it is a bad practice. Let me show you…
// bad
const styleGuide = require('./styleGuide');
module.exports = styleGuide.es6;
// ok
import styleGuide from './styleGuide';
export default styleGuide.es6;
// best
import { es6 } from './styleGuide';
export default es6;
Use import and export keywords instead of require. Using curly brackets is the best practice for importing any module.
8) Properties
Many new developers use third brackets when accessing the properties of an object. But it is a bad practice. A good practice is using dot “.” notation during accessing properties of an object. Here is an example…
const luke = {
  jedi: true,
  age: 28,
};
// bad
const isJedi = luke['jedi'];
// good
const isJedi = luke.jedi;
9) Exponentiation Operator
Use exponentiation operator ** when calculating exponentiation. Though you can use Math.pow() to do the same stuff. But the exponential operator is the best practice for calculating exponentiation. Here is an example…
// bad
const binary = Math.pow(2, 10);
// good
const binary = 2 ** 10;
10) Comparison Operators
Use === and !== over == and != . Because === will check the value and the type but == will not check the type whether it is string or integer.
You should use shortcuts for booleans, but explicit comparisons for strings and numbers. It will keep your code more cleaner…
// bad
if (isValid === true) {
  // ...
}
// good
if (isValid) {
  // ...
}
// bad
if (name) {
  // ...
}
// good
if (name !== '') {
  // ...
}
// bad
if (collection.length) {
  // ...
}
// good
if (collection.length > 0) {
  // ...
}
