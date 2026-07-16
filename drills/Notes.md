# NOTES.md

## 1. What is the difference between `let` and `const`? When would you use each?

`const` is used when a variable should not be reassigned after it is created. I use `const` by default because it prevents accidental changes and makes the code easier to understand.

`let` is used when the value of a variable needs to change later, such as counters in loops or values that are updated over time.

For example:

```js
const name = "Aarav";
let count = 0;

count++;
```

`name` never changes, so `const` is appropriate. `count` changes, so `let` is needed.

---

## 2. Explain `map`, `filter`, and `reduce` to someone who has never seen them.

### `map`

`map` transforms every item in an array into something new while keeping the same number of items.

Example:

```js
[1, 2, 3].map(n => n * 2);
// [2, 4, 6]
```

---

### `filter`

`filter` keeps only the items that satisfy a condition and removes the rest.

Example:

```js
[1, 2, 3, 4].filter(n => n % 2 === 0);
// [2, 4]
```

---

### `reduce`

`reduce` combines all items in an array into a single value such as a total, average, count, or object.

Example:

```js
[1, 2, 3, 4].reduce((sum, n) => sum + n, 0);
// 10
```

---

## 3. What is a closure? Use an example from your own drill code.

A closure is a function that remembers variables from the place where it was created, even after the outer function has finished running.

The `makeCounter()` drill is an example of this:

```js
const counter = makeCounter();

counter.increment(); // 1
counter.increment(); // 2
```

The `increment()` function still remembers the `count` variable even though `makeCounter()` already finished executing.

Each counter gets its own separate `count` variable, which is why different counters do not interfere with each other.

--- 

## 4. What does an "immutable update" mean, and why not simply change the original array?

An immutable update means creating a new array or object with the changes instead of modifying the original one.

For example, instead of:

```js
students.push(newStudent);
```

I would write:

```js
const updatedStudents = [...students, newStudent];
```

This is important because changing the original data can cause bugs that are difficult to track down. In React, immutable updates also help React detect changes and update the UI correctly.

---

## 5. What is the difference between `value ?? fallback` and `value || fallback`? When does it matter?

`||` uses the fallback whenever the value is considered "falsy", including:

* `false`
* `0`
* `''`
* `null`
* `undefined`

`??` only uses the fallback when the value is `null` or `undefined`.

Example:

```js
0 || "Unknown"
// "Unknown"
```

This is incorrect if `0` is a valid value.

```js
0 ?? "Unknown"
// 0
```

This is usually what I actually want.

This matters when values like `0`, `false`, or an empty string are valid data and should not be replaced.

---

## 6. What does `await` actually do? What is the difference between doing three things one after another and doing all three at once?

`await` pauses the current async function until a promise finishes and returns its result. It does not stop the entire program — only that specific async function waits.

Doing tasks one after another looks like this:

```js
await load(1);
await load(2);
await load(3);
```

This is sequential execution. If each task takes 50 milliseconds, the total time is about 150 milliseconds.

Doing them all at once looks like this:

```js
await Promise.all([
  load(1),
  load(2),
  load(3)
]);
```

This is parallel execution. All three tasks start immediately, so if each takes 50 milliseconds, the total time is still about 50 milliseconds.

Sequential execution is useful when each step depends on the previous result. If the tasks are independent, `Promise.all()` is usually faster.
