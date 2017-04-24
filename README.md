# easy-immutable
A light weight implementation of an immutable object. You can pass this object around to ensure data safety through out your application.


## Usage
The usage is simply to pass an existing object into the Immutable to receive an object of type Immutable with all the same properties of the original object

```
const im = new Immutable({ foo: 'bar });
console.log(`foo is ${im.foo}`);     // results in 'foo is bar'
```

The immutable will enumerate down through the object structure including arrays, only primitive types like strings, numbers, etc will be excluded
```
const im = new Immutable({ one: { foo: 'bar' } });
console.log(R.is(Immutable, im.one));    // results in true
```

## Errors
Trying to set a value on an immutable object will result in an TypeError being thrown

```
const im = new Immutable({ foo: 'bar' });
im.foo = 'baz';     // received a TypeError
``` 
