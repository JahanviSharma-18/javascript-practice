# javascript-practice

This repository contains my work for Week 3 of the React Native Internship Program.

The purpose of this week was to become comfortable with the JavaScript concepts that future weeks of the program will build upon.

## Topics Practised

### JavaScript Fundamentals

* `let` and `const`
* Arrow functions
* Template literals
* Default parameters
* Destructuring
* Spread and rest operators
* Optional chaining (`?.`)
* Nullish coalescing (`??`)

### Working with Data

* `map()`
* `filter()`
* `find()`
* `reduce()`
* `some()`
* `every()`
* Immutable array and object updates

### Functions and Closures

* Functions as values
* Higher-order functions
* Returning functions from functions
* Closures
* Pure functions

### Asynchronous JavaScript

* Promises
* `async` / `await`
* `try` / `catch`
* `Promise.all()`
* Sequential vs parallel execution

---

## Files Included

* `01-basics.js`
* `02-arrays.js`
* `03-objects.js`
* `04-functions.js`
* `05-async.js`
* `NOTES.md`

---

## What I Found Difficult

The topic I found most challenging was `reduce()`. Understanding the accumulator and how it changes during each iteration took some time and practice.

Closures were also difficult at first because it was not immediately obvious how a function could continue to access variables after the outer function had already finished executing.

The difference between sequential and parallel async operations using `await` and `Promise.all()` was another concept that required some experimentation before it became clear.

---

## What Finally Made Sense

Writing my own version of `map()` in `applyToAll()` helped me understand what higher-order functions are doing internally.

Building `makeCounter()` made closures much easier to understand because I could see how the returned functions continued to remember the `count` variable.

Comparing `loadAll()` and `loadInOrder()` side by side made the difference between parallel and sequential execution much clearer.

I also became much more comfortable with immutable updates using spread syntax instead of modifying arrays and objects directly.

---

## Reflection

This week focused entirely on strengthening JavaScript fundamentals rather than building an application.

The exercises provided immediate feedback through tests, which made it easier to identify mistakes and understand concepts before moving on.

By the end of the week, I felt significantly more confident working with array methods, closures, immutable updates, and asynchronous JavaScript.
