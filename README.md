# Promise Examples
 - Just examples of how to use promise
 
# Code 
``` 
const resolvePromise = true //change to "false" if you want to reject promise

const promise = new Promise((resolve, reject) => resolvePromise ? resolve(1) : reject(0))
```

*//then/catch version*

```
promise.then(result => {
    console.log("result: ", result); 
    //"result: 1" in console if resolvePromise = true
}).catch(error => {
    console.log("error: ", error); 
    //"error: 2" in console if resolvePromise = false
})
```

*// async/await version*

```
async function execute() {
    try {
        const result = await promise
        console.log("result: ", result); 
        //"result: 1" in console if resolvePromise = true
    } catch (error) {
        console.log("error: ", error); 
        //"error: 2" in console if resolvePromise = false
    }
}
execute();
```

*// async/await version with arrow function*

```
;(async () => { //";" to js understand this shit
    try {
        const result = await promise
        console.log("result: ", result); 
        //"result: 1" in console if resolvePromise = true
    } catch (error) {
        console.log("error: ", error); 
        //"error: 2" in console if resolvePromise = false
    }
})() //"()" to self-call the function
```
