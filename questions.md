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

# 9

console.log(typeof typeof 100)

OUT- string

# 10

const arr = [...'Adi'];
console.log(arr);

OUT- [ 'A', 'd', 'i' ]

# 11

write a function that returns reverse of a string

function reverse(str){
let revstr=""
for (let index = str.length - 1; index >= 0; index--) {
revstr+=str[index]
}
return revstr
}
console.log(reverse("Hi I am Adi"))

OR

function reverse(str){
return str.split("").reverse().join("")
}
console.log(reverse("Hi I am Adi"))

//it would first spilt it into array then reverse the array order,then join to form a string again.

# 12

write a function that prints longest word in a sentence

function longest(str){
let arr = str.split(" ");
let max = arr[0].length;
let long=""
for (let i = 1; i < arr.length; i++) {
if(arr[i].length>max){
max=arr[i].length;
long=arr[i];
}
}
return long;
}
console.log(longest("I love coding in javascript"))

# 13

Write a function that checks whether a given string is pallindrome or not?

function isPalindrome(str){
let revstr = str.split("").reverse().join("")
return revstr===str
}
console.log(isPalindrome("hihihihi"))

# 14

write a function to remove duplicate elements from an array

function duplicate(arr){
let uniq = []
for(let i of arr){
if(uniq.indexOf(i)===-1){
uniq.push(i)
}
}
return uniq
}
console.log(duplicate([2,2,3,4,5,6,6]))

OR

function duplicates(arr){
return [...new Set(arr)]
}
console.log(duplicates([2,2,3,4,5,6,6]))

# 15

write a function that checks whether two strings are anagram or not?

function areAnagrams(an1,an2){
return [...new Set(an1.split(""))].sort().join("") === [...new Set(an2.split(""))].sort().join("")
}

console.log(areAnagrams("silent","listen"))

We can do it without set,like normally manipulating the strings too .

# 16

write a function that returns number of vowels in a string

function noOfVowels(str){
str=str.toLowerCase()
let count=0
let vowels = ['a','e','i','o','u']
for(let i of str){
if(vowels.indexOf(i)!=-1){
count++
}
}
return count
}
console.log(noOfVowels("Adi"))

# 17

write a function to check if a number is prime or not

function isPrime(num){
for(let i=2;i<=Math.sqrt(num);i++){
if(num%i===0){
return false
}
}
return true
}

# 18

write a function to return the factorial of a number

function factorial(num){
if(num===0){
return 1
}
let fact=1
for(let i=1;i<=num;i++){
fact\*=i
}
return fact
}
console.log(factorial(5))

# 19 

what is temporal dead zone?

The Temporal Dead Zone is the time between when a variable is declared and when it is initialized — during this time, you cannot access the variable.
It happens with variables declared using let and const.
The Temporal Dead Zone (TDZ) is a specific behavior in JavaScript (introduced with ES6 let and const declarations) related to the period between entering a scope and where a let or const variable is declared.
Contrast with var: Variables declared with var are "hoisted" to the top of their function scope (or global scope) and are initialized with the value undefined. You can access a var variable before its declaration line without an error (you'll just get undefined). let and const variables are also technically hoisted (the engine knows about them at the start of the scope), but they are not initialized. They remain in the TDZ, inaccessible, until the line with their declaration is executed.

# 20 

Difference between spread and rest ?

```
//The spread operator expands an iterable(like an array or object) into individual elements.

const user = {
  id: 42,
  name: 'Bob',
  age: 35,
  isAdmin: false,
  address: {
    street: '123 Main St',
    city: 'Anytown',
  },
};

const user2 = { ...user };

//The rest parameter collects multiple elements into a single array.It's typically used in function parameters.

const { id, name, ...rest } = user;
console.log(id);
console.log(name);
console.log(rest);
```
