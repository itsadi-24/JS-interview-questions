```
const arr = [1, 2, 3, 4, 5];
arr.forEach((num) => {
  num = num * 2;
  console.log('The elements are', num);
});
// it returns undefined as it doesnt creates a new array,when we are performing any operations its only performed on the local variable num
console.log(arr);
// Here the original array remains unchanged

const arr2 = arr.map((num) => {
  console.log(num);
  return num * 2;
});
console.log(arr);
console.log(arr2);
// it also doesnt changes the original array,instead it creates a new one

const arr3 = arr.filter((num) => {
  if (num % 2 == 0) {
    return num;
  }
});
console.log(arr);
console.log(arr3);
// its the same as map but only returns the values that satisfy the condition

const numbers = [1, 2, 3, 4, 5];
const sum = numbers.reduce((accumulator, currentValue) => {
  return accumulator + currentValue;
}, 0);
console.log(sum); 
//The reduce() function in JavaScript is a powerful array method that allows you to process all elements in an array to produce a single output value. It essentially "reduces" an array to a single value by applying a callback function to each element.
```
