# Snippets
## Deadlock
```ts
export {}

let barPromise: Promise<void> | undefined;
let fooPromise: Promise<void> | undefined;

async function bar(): Promise<void> {
    console.log("bar start");

    return new Promise((resolve, reject) => {
        console.log("bar delay");

        setTimeout(() => {
            console.log("bar await");

            fooPromise!.then(() => {
                console.log("bar resolve");
                resolve();
            })
        }, 1000)
    });
}

async function foo(): Promise<void> {
    console.log("foo start");

    return new Promise((resolve, reject) => {
        console.log("foo delay");

        setTimeout(() => {
            console.log("foo await");

            barPromise!.then(() => {
                console.log("foo resolve");
                resolve();
            })
        }, 1000)
    });
}

barPromise = bar();
fooPromise = foo();

Promise.all([barPromise, fooPromise]).then(() =>{
    console.log("All done");
});

```