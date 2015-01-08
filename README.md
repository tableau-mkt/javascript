# JavaScript Style Guide, extended () {

*An approach to JavaScript beyond reasonable*

## Table of Contents

  1. [Hoisting](#hoisting)
  1. [Conditional Expressions & Equality](#conditional-expressions--equality)

## Hoisting

  - Variables only used as a loop index or counter do not need to be hoisted to the top of their scope. You certainly can in order to help avoid accidental/unexpected value, but it's not required.

```javascript
var thingList = [],
    handyDandy = true;

for (var thing in thingList) {
  console.log(thing);
}
```

**[⬆ back to top](#table-of-contents)**


## Conditional Expressions & Equality

  - Conditional statements including an `else` clause should be structured as such: bracket on the same line as else, code indented on the next line.

```javascript
if (false) {
  // Not likely.
}
else {
  // This will definitely happen.
  // Yulp.
}
```

  - Conditional statement clauses that only contain one line of executed code *may* be placed on one line. However, readability and consistency should always preceed space savings.

```javascript
if (false) { console.log('not likely'); }
else { console.log('For sure'); }
```

**[⬆ back to top](#table-of-contents)**

## Contributors

  - [Tasty Nerd Tapas](https://twitter.com/nerdtapas)

# };
