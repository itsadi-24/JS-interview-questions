# What is Promise?
Promise is a special object,it is a placeholder for the result of any asynchronous operation.It has 3 states :- pending, fullfilled and rejected

```
console.log("Making api call")
fetch('https://fakestoreapi.com/products/1')
.then(response => {
    console.log('Data is Parsing')
    return response.json()
}).then(data=>{
    console.log('The Data is ',data)
}).catch(error => {
    console.log('Error',error)
}).finally(()=>{
    console.log("API call completed")
})
```

# Disadvantages of promises
Okay, while Promises are a massive improvement over old-style callbacks, they aren't perfect and have led to even better solutions.
Here are some disadvantages or complexities associated with Promises:
Disadvantages/Complexities of Promises:

    Verbosity/Chaining Can Still Be Clunky: While better than callback hell, long chains of .then().then().then()... can still become hard to read, especially if you have conditional logic inside them. You have to keep passing results down the chain.
    Error Handling Nuances:
        If you forget to add a .catch() at the end of a chain, a rejected Promise might "disappear" silently (though modern environments often warn about "unhandled rejections").
        An error thrown inside a .then() callback will cause the next .catch() to trigger, which is usually what you want, but can sometimes be surprising if you're not expecting it. You need to be careful about where you place your .catch() blocks.
    Debugging Can Be Tricky: Debugging asynchronous code is inherently harder than synchronous code. While Promises help, tracing the flow through multiple .then() calls and understanding the call stack at the point of an error can still be challenging compared to step-by-step synchronous execution.
    Slight Learning Curve: Understanding the states (pending, fulfilled, rejected), how resolve and reject work, and the rules of chaining takes some initial effort.
    Easy to Forget return: Inside a .then(), if you perform an action but forget to return a value (or another Promise), the next .then() in the chain will receive undefined, which can break the flow in unexpected ways.


#Async/Await

```
async function fetchProd() {
  console.log('The Api call has been made');
  try {
    const resp = await fetch('https://fakestoreapi.com/products/2');
    const data = await resp.json();
    console.log('The data is', data);
  } catch (error) {
    console.log(error);
  } finally {
    console.log('The api call is over');
  }
}
fetchProd();
console.log('Making API call');
```


# Callbacks:
A callback is just a function that gets passed on to another function which is called when certain conditions meet or when needed.

```
function abc(xyz) {
  console.log('This is inside ABC');
  xyz(def);
  console.log('This is inside ABC after XYZ()');
}
function xyz(def) {
  console.log('This is inside XYZ');
  def();
  console.log('This is inside XYZ after DEF()');
}
function def() {
  console.log('This is inside def');
}
abc(xyz);
```
