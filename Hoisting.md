why is hoisting not happening in this case or is it happening?

```javascript
printSomething()
let a = 5
let b = 5
function printSomething(){
console.log(a+b)
}
```
i am getting error as
ERROR!
/tmp/UYZzZSHKP0/main.js:8
console.log(a+b)
^
ReferenceError: Cannot access 'a' before initialization
##Answer##

Okay, let's try a really simple way to think about it.

Imagine JavaScript reads your code in two passes:

**Pass 1: Getting Ready**

*   JavaScript quickly scans your code for *declarations* (like saying "Hey, there will be a function called `printSomething`" and "Hey, there will be variables called `a` and `b`").
*   For **functions** (like `function printSomething(){...}`), it remembers the *whole function* right away. It's fully ready.
*   For **`let` variables** (like `let a` and `let b`), it remembers their *names* (`a`, `b`) but puts them in a special "hands-off zone". It knows they exist, but you can't use them yet. Think of it like reserving a parking spot – the spot is reserved (`a` exists), but the car isn't there yet, so you can't use the car.

**Pass 2: Running the Code (Line by Line)**

1.  **Line 1: `printSomething()`**
    *   JavaScript says: "Okay, run the `printSomething` function." (It knows the function because of Pass 1).
    *   **Inside the function:** It sees `console.log(a + b)`.
    *   It asks: "What is `a`? What is `b`?"
    *   JavaScript remembers from Pass 1 that `a` and `b` exist, but they are still in the "hands-off zone" because we haven't reached the lines `let a = 5` and `let b = 5` yet in this running pass.
    *   **ERROR!** You can't use `a` or `b` while they are in the "hands-off zone".

2.  **Line 2: `let a = 5`**
    *   Now, JavaScript takes `a` out of the "hands-off zone" and gives it the value `5`. Now `a` is ready to use *from this point forward*.

3.  **Line 3: `let b = 5`**
    *   Now, JavaScript takes `b` out of the "hands-off zone" and gives it the value `5`. Now `b` is ready to use *from this point forward*.

4.  **Line 4: `function printSomething(){...}`**
    *   JavaScript already knows about this function from Pass 1, so it just skips over the definition here.

**The Problem in Short:**

You called the function (`printSomething()`) *before* the code reached the lines that make `a` and `b` ready to use (`let a = 5`, `let b = 5`). Even though JavaScript *knew* `a` and `b` would exist later (hoisting), they weren't usable *yet* (Temporal Dead Zone).

**The Fix:** Just move the function call (`printSomething()`) *after* you make `a` and `b` ready:

```javascript
let a = 5; // Make 'a' ready
let b = 5; // Make 'b' ready
function printSomething(){
    console.log(a + b); // Now 'a' and 'b' are ready when this runs
}
printSomething(); // Call the function now - it works!
```

Note:- Now for "var" we will get NaN as the output because the temporal dead zone doesnt exists for var.
When var is hoisted, it's automatically initialized with the value undefined. It's not put in a "hands-off zone" like let. Think of it like the parking spot is reserved and a placeholder sign (undefined) is put there immediately.
