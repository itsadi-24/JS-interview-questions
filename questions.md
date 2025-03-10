# 1

let num = [1,2,3,4,5]
let num2 = num.filter(i => i=2)
console.log(num2)

Output: [1,2,3,4,5] because truthy value when compared with 2 is 1, so it will return all the elements in the array. If i=0 then we get [] as output.

# 2

A ReferenceError in JavaScript occurs when your code tries to access a variable that hasn't been declared or is out of scope

# 3

ES6 features:

1. Arrow functions
2. block scoped variables(let, const)
3. template literals

# 4

what is reference error?
A ReferenceError in JavaScript occurs when your code tries to access a variable that hasn't been declared or is out of scope

# 5

what is temporal dead zone?

The Temporal Dead Zone is a behavior in JavaScript that occurs when declaring a variable with the let and const keywords, but not initializing it.It's a period of time where let and const variables exist in memory, but cannot be accessed.

# 6

what is the difference between local storage and session storage?

Both local storage and session storage are part of the Web Storage API in modern browsers, and they let you store key-value pairs on the client side. However, they differ in their persistence and scope:

    Local Storage:
        Persistence: Data remains even after the browser is closed and reopened.
        Scope: Shared across all tabs and windows of the same origin.
        Use Case: Suitable for data that should persist over long periods, like user preferences or saved state.

    Session Storage:
        Persistence: Data is cleared when the tab or browser window is closed.
        Scope: Limited to the tab or window that created it; different tabs have separate session storage.
        Use Case: Ideal for temporary data that should only last for a single browsing session, such as data input on a multi-page form.

# 7

function abc(){
console.log(abc.xyz)
}
abc()
abc.xyz=400
abc.xyz=200
abc()

# 8

const num = [1,2,3]
num[50]=100
console.log(num)

OUTPUT - [ 1, 2, 3, <47 empty items>, 100 ]
