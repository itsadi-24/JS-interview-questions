Lexical Scoping - It tells us that we can access a variable in its own scope or its parent,but from parent we cant accept a childs variable

```javascript
{
    let a = "Adi"
    {
        let b = "Prasan"
        console.log(a)
        {
            let c = "Khuntia"
            console.log(b)
        }
        console.log(c)
    }
    {
        console.log(b)
    }
}
```

Closure - Closure is created when the inner function has the access to the variable of the outer function even after the outer function is executed 

```javascript
function outerFunction(){
    let outerVar = "Adi"
    function innerFunction(){
        let innerVar = "Prasan"
        // console.log(outerVar)
    }
    function innerFunction2(){
        // console.log(innerVar)
        console.log(outerVar)
    }
    innerFunction()
    innerFunction2()
}
outerFunction()
```
