`In JS there are two ways to copy and object,shallow copy and deep copy`

# Shallow Copy
In shallow copy it copies the object but only reference to the nested objects.(A shallow copy creates a new object/array, but only copies references to nested objects)

``Object spread: {...originalObject}
Array spread: [...originalArray]
Object.assign({}, originalObject)``

```javascript
let obj = {
    name : 'Adi',
    address:{
        city:'Rourkela'
    }
}
console.log("1st",obj)
let obj2 = {...obj}
obj2.address.city = 'Bhubaneshwar'
console.log("2nd",obj)
```

# Deep Copy 
A deep copy creates a completely independent clone, duplicating all nested objects 

```javascript
let obj = {
    name : 'Adi',
    address:{
        city:'Rourkela'
    }
}
console.log("1st",obj)
// let obj2 = {...obj}
// obj2.address.city = 'Bhubaneshwar'
// console.log("2nd",obj)

let obj2 = JSON.parse(JSON.stringify(obj))
obj2.address.city='Delhi'
console.log("2nd",obj2)
```
