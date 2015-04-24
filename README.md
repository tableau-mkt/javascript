# JavaScript Style Guide, extended () {

*An approach to JavaScript beyond reasonable*

## Table of Contents

  1. [Hoisting](#hoisting)
  1. [Conditional Expressions & Equality](#conditional-expressions--equality)
  1. [Naming Convention](#naming-convention)


## Function Params

The second paramter passed to a function should probably be an options object; once you need three you really must-- and you'll really wish you'd done so already.

```javascript
function myFunction($data) { // Tidy :)

function myFunction($options) { // Flexible :)

function myFunction($controller, $options) { // Forethought :)

function myFunction($oneThing, $yetAnother) { // Slippery slope :(

function myFunction($oneThing, $yetAnother, $evenMore) { // Please don't
```


## Hoisting

Variables only used as a loop index or counter do not need to be hoisted to the top of their scope. You certainly can hoist to help avoid accidental collision /unexpected value, but it's not required.

```javascript
var thingList = [],
    someVar = true;

for (var thing in thingList) {
  console.log(thing);
}
```

**[⬆ back to top](#table-of-contents)**


## Conditional Expressions & Equality

Conditional statements including an `else` clause should be structured as such: else on a new line from closing bracket and on the same line as opening bracket, of course code indented within clause.

```javascript
if (false) {
  // Not likely.
}
else {
  // Will definitely happen.
}
```

Conditional statements with mulitple clauses including an operator should include explicit parenthesis.

```javascript
if ((typeof myObj.myVar === 'string') && checkStuff()) {
  // Wasn't that nice?
}

while ((counter >= 0) && (failSafe !== true)) {
  // Easier to read.
}
```


Conditional statements that only contain one **short** piece of executed code *may* be placed on one line, (including only one space.) Short is defined as...

- `return;`
- `return true;`
- `return false;`
- `myNoArgFunc();`
- `myFunc(var);`

```javascript
if (typeof myVar !== 'object') return false;
else if (myVar.processeed) return;
else processVar(myVar);
```

However, readability and consistency should always preceed space savings!

**[⬆ back to top](#table-of-contents)**

## Naming Convention

### Use lowerCamelCase

Use lowerCamelCase for naming variables and function names. Only two letter acronyms should be uppercased.

```javascript
var someVariableName,
    someUrl,
    someCdn,
    someAwesomeIODomain;
```

**[⬆ back to top](#table-of-contents)**

## Contributors

  - [Tasty Nerd Tapas](https://twitter.com/nerdtapas)

# };
