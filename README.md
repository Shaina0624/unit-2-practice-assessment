# Unit 2 Practice Assessment - JavaScript Foundations

## Short Responses 

1. **The function declaration comes _after_ the variable declaration in the code below. What will happen when it this code runs?**
```javascript
let greeting = "Hello!"

function sayItLoud() {
  console.log(`${greeting}!!!`)
}

sayItLoud();
```
`Hello!!!!` would be logged because `greeting` has been already declared by the variable, `let` before the function declaration. Function declaration defines a function with a specific parameter while function expression is when it is being immediately invoke the expression by the variable.


2. **Okay... so why does the code below throw an error?**
```javascript
sayItLoud();

function sayItLoud() {
  console.log(`${greeting}!!!`)
}

let greeting = "Hello"
```

It will throw an `error` beacuse the expression, `sayItLoud();` is in invoked but not declared. `greeting` is declared, `let greeting = "Hello"`, after the fuction declaration `function sayItLoud() {
  console.log(`${greeting}!!!`)
}`. The variable `let` is being used which is a block scope that cannot be used anywhere, like after, the function block.

3. **Mmhmmm... so what about this😰. What does the following code log? Why?**
```javascript
sayItLoud();
function sayItLoud() {
  console.log(`${greeting}!!!`)
}
var greeting = "Hello"
```

`undefined` because 'var' or any other variable has to declare `greeting` before the `console.log` that is in the function and the expression `sayItLoud();` has to be invoked before or after the function declaration.

4. **Why does the following block of code throw an error? How can we fix this without changing the variable declaration keyword?**
```javascript
const isSunny = true;

if (isSunny) {
  let status = 'No umbrella needed!';
} else {
  let status = 'Better wear a raincoat!'
}

console.log(status);
```
**tags:** #variableScope
**key:** "let is block scoped"

`error` is being logged because `console.log(status);` needs to be logged after `let status = 'No umbrella needed!'` and/or `let status = 'Better wear a raincoat!'` before the semicolon. This is because `let` is a block scope meaning that the `console.log` statement would need to be within the brackets `{}`.

5. **Why does the following block of code NOT throw an error?**
```javascript
const isSunny = true;

if (isSunny) {
  var status = 'No umbrella needed!';
} else {
  var status = 'Better wear a raincoat!'
}

console.log(status);
```
**tags:** #variableScope
**key:** "variables declared with var are not block scoped"

Referring back to Question 5, `var` is a global and function scope while `let` and `const` are a block scope. the `console.log(status);` does not need to be within the brackets `{}`, or the block of code. 

6. **In JavaScript, we can declare variables with `var`, `let`, and `const`. What are the differences between each? Be sure to comment on how each declaration impacts the _scope_, _reassignment_, and _hoisting_ of variables.**

- `var` is the only varible that can be hoisted and is scoped globally and through a function. It can also be used to reassign variables to different values. It is the most flexible declaration of the varibles.
- `let`, simliarly to `const`, it can never be hoisted and it can be used in a block scope. Like `var`, variables can be reassigned using declaration.
- `const` is the least flexible declaration of the variables because it cannot be hoisted or reassigned. It has to declare varibles inside the block scope  `{}`.

7. **Where does the following code throw an error? What type of error? Why?**
```javascript
let a = b;

console.log(a);
```
**tags:** #variableDeclaration
**key:** "the variable `b` is not defined."

`error` because `b` is not defined. It has no value. It'd work if `b` is converted into a string, `"b"` because strings do have value. 

8. **What is the value of `y` after this code runs? Explain why this is the case.**
```javascript
let x = 1;
let y = x;
x += 1;

console.log(x);
console.log(y);
```
**tags:** #mutability
**key:** "`y` points to the integer `1`, a primitive data type", "reassigning `x` has no effect on `y`" 

`y` has the value of 1 always despite having `x += 1;`, which is `x` being reassigned, the value of `y` would not change because `x` was redeclared after `y` was declared. 

9. **What does the following code log? Explain why?**
```javascript
let a = {goals: "Enmanuel"};
let b = a;
a.goals = "Cielo";
console.log(b.goals);
```
**tags:** #mutability
**key:** "`b` points to the same object referenced by `a`"

`b.goals` logs to `"Cielo"` because `b` is assigned as `a` which means that whichever value `a` is assigned as `b` will also have the same value.

10. **Where does the following code throw an error? What type of error? Why?**
```javascript
const fellows = 'Itzel Carmen';
fellows = 'Itzel Carmen Shemar';

console.log(fellows);
```
**tags**: #variableDeclaration #mutability #primitives
**key:** "variables declared with `const` cannot be reassigned"



11. **Wait, why doesn't the code below throw an error?! 🧐 What does this demonstrate?**
```javascript
const fellows = ['Itzel', 'Carmen'];
fellows.push('Shemar');

console.log(fellows);
```
**tags:** #mutability #objects
**key:** "`fellows` was not reassigned", "JavaScript objects are mutable"



12. **What does the following code log? Why?**
```javascript
let greeting = "What's up?";

function say() {
 return `${greeting}! 🤟🏿`
}

console.log(say);
```
**tags**: #functionExecution #functionArguments
**key:** "function was not invoked"



13. **What does the following code log? What does this say about JavaScript function arguments?**
```javascript
function shoutOut() {
  console.log(`The flyest person in the room is Carmen!`);
}

shoutOut('Devonte');
```
**tags:** #functionExecution #variableScope
**key:** "arguments are optional", "extraneous arguments are ignored"



14. **What happens if a function is invoked with fewer arguments than there are parameters? Include a code snippet to illustrate.**

**tags:** #functionExecution #functionArguments
**key:** "missing parameters are set to `undefined`"



15. **What about extra parameters? How can we access them and use them to our advantage? Illustrate by writing a function that takes any number of integers as arguments and returns their sum.**

Example:
```javascript
sum(1, 2, 10); // 13
sum(5); // 5
sum(100, 200, 800, 1, 1, 1); // 1103;
```
**tags:** #functionExecution
**key:** the array-like `argument` object, the ES6 rest parameter syntax



16. **What does the following code log? Why?**
```javascript
let bestCoder = 'Laura';

function shoutOut() {
  bestCoder = 'Motun';
}

shoutOut();
console.log(`The best coder in the room is ${bestCoder}`.);
```
**tags:** #variableScope
**key:** "functions have access to variables defined in their local scope and all surrounding scopes"



17. **What does the following code log? Why?**
```javascript
let theGoat = 'Reuben';

function shoutOut() {
  let theGoat = `Maya`;
  console.log(`${theGoat} is the hardest working person in the room.`);
}

shoutOut();
console.log(`${theGoat} is also the hardest working person in the room.`);
```
**tags:** #variableScope
**key:** "lexical scope"



18. **What does the following code log? Why?**
```javascript
let theCEO;

function hire(theCEO) {
  theCEO = 'Mark';
}

hire(theCEO);
console.log(`I have no doubt that ${theCEO} will be running a company of his own very soon. I just hope that he will hire me when I need a job.`);
```
**tags:** #variableScope
**key:** "variable shadowing" the function declarations creates a _new_ local variable declaration for its parameter, `theCEO`."



19. **What does it mean to _pass by value_? For what data types does JavaScript _pass by value_? Use a code snippet to illustrate.**

**tags:** #mutability #functionExecution
**key:** "primitive data types are passed by value"



20. **What does it mean to _pass by reference_? For what data types does JavaScript  appear to _pass by reference_? Use a code snippet to illustrate.**

**tags:** #mutability #functionExecution
**key:** "JavaScript objects are passed by reference"



21. **Explain why the first code snippet below throws an error, but the second does not.**

```javascript
10 + a;        // ReferenceError: a is not defined
```

```javascript
let a = {};
10 + a.x;      // Evaluates to NaN
```
**tags:** #objects
**key:** "undefined properties of objects return `undefined`"



22. **What is the relationship between JavaScript Objects and JavaScript Arrays? We say a JavaScript Object is _empty_ if it has no properties of its own. We say that a JavaScript Array is _empty_ if it has no _elements_. How do we check for emptiness of JavaScript Objects? How do we check for emptiness of JavaScript Arrays. Use code snippets to illustrate your answer.**

**tags:** #objects #arrays
**key:** "JavaScript arrays are objects", "use `.length` to check for array emptiness", "use Object.keys(object) to check for object emptiness"



## Problem Set
1. Write a function that takes a string, doubles every consonant character in the string, and returns the result as a new string. The function should not double vowels (``'a'``,``'e'``,``'i'``,``'o'``,``'u'``), digits, punctuation, or whitespace.

Examples:
```javascript
doubleConsonants('String');          // "SSttrrinngg"
doubleConsonants('Hello-World!');    // "HHellllo-WWorrlldd!"
doubleConsonants('July 4th');        // "JJullyy 4tthh"
doubleConsonants('');                // ""
```



2. Write a function that takes a string and returns the string reversed.

Examples:
```javascript
reverse('Test'); // "tseT"
reverse('anotherTest'); // "tseTrehtona"
reverse('factor In spaces'); // "secaps nI rotcaf"
reverse(''); // ""
```



3. Write a function takes an integer `year` as an argument and returns a boolean based on whether the year is a leap year. Note: Every year that is evenly divisible by 4 is a leap year, except every year that is evenly divisible by 100, unless the year is also evenly divisible by 400.

Examples:
```javascript
isLeapYear(1997); // false
isLeapYear(1996); // true
isLeapYear(1900); // false
isLeapYear(2000); // true
```


4. Write a function that combines two arrays into one new array. The new array should start with an item from the first array argument, then an item from the second array argument, and then alternates. You can assume the two input arrays are the same length.

Example:
```javascript
combineArrays([1, 2, 3], [4, 5, 6]);      // [1, 4, 2, 5, 3, 6]
combineArrays(['a', 'b'], ['x', 'y']);    // ['a', 'x', 'b', 'y']
combineArrays([true], [false]);           // [true, false]
```

5. Write a function that returns an object that shows how many times each vowel shows up in a sentence (vowels are `'a'`, `'e'`, `'i'`, `'o'`, and `'u'`). The returned object should have exactly 5 key-value pairs, one for each vowel (the value shold be the number of times that vowel appears in the sentence). 

Example:
```javascript
countVowels('Hello World');                                     // {'a': 0, 'e': 1, 'i': 0, 'o': 2, 'u': 0}
countVowels('The quick brown fox jumped over the lazy dog');    // {'a': 1, 'e': 3, 'i': 1, 'o': 4, 'u': 2}
countVowels('Over the Marcy Lab School');                       // {'a': 2, 'e': 1, 'i': 0, 'o': 3, 'u': 0}
```


6. Write a function that takes a sentence string as an argument, and returns that string with every occurrence of a "number word" — `'zero'`, `'one'`, `'two'`, `'three'`, `'four'`, `'five'`, `'six'`, `'seven'`, `'eight'`, `'nine'` — converted to its corresponding digit character.

Example:
```javascript
wordToDigit('Please call me at five five five one two three four. Thanks.');
// "Please call me at 5 5 5 1 2 3 4. Thanks."
```



7. For a game of Dungeons & Dragons, each player starts by generating a character they can play with. This character has, among other things, six abilities; strength, dexterity, constitution, intelligence, wisdom and charisma. These six abilities have scores that are determined randomly. You do this by rolling four 6-sided dice and record the sum of the largest three dice. You do this six times, once for each ability.

Your character's initial hitpoints are 10 + your character's constitution modifier. You find your character's constitution modifier by subtracting 10 from your character's constitution, divide by 2 and round down.

Write a random character generator function that follows the rules above.

For example, the six throws of four dice may look like:
  * 5, 3, 1, 6: You discard the 1 and sum 5 + 3 + 6 = 14, which you assign to strength.
  * 3, 2, 5, 3: You discard the 2 and sum 3 + 5 + 3 = 11, which you assign to dexterity.
  * 1, 1, 1, 1: You discard the 1 and sum 1 + 1 + 1 = 3, which you assign to constitution.
  * 2, 1, 6, 6: You discard the 1 and sum 2 + 6 + 6 = 14, which you assign to intelligence.
  * 3, 5, 3, 4: You discard the 3 and sum 5 + 3 + 4 = 12, which you assign to wisdom.
  * 6, 6, 6, 6: You discard the 6 and sum 6 + 6 + 6 = 18, which you assign to charisma.
Because constitution is 3, the constitution modifier is -4 and the hitpoints are 6.

Your function should take one argument, a `name`. It should generate random attribute values using `Math.rand()`. The function should return a JavaScript Object that contains all of the above attributes.

Example:
```javascript
characterGenerator("Elminster");

/*
{
  name: "Elminster"
  strength: 10,
  dexterity: 8,
  constitution: 12,
  intelligence: 14,
  wisdom: 12,
  charisma: 18,
  hitpoints: 11
}

*/
```
