Every
=====

JavaScript has an `every` ([MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/every)) method on Arrays that accepts a callback function to check if each element in the array passes that validation and then returns a Boolean, if so.

```javascript
[0, 1, 2, 3, 4].every( function( element, index, array ) {
  return element < 5;
} ); // returns true
```
