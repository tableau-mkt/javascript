# JavaScript Style Guide, extended () {

*An approach to JavaScript beyond reasonable*
Don't be afraid to make rules for: readability, future-proofing, and elegance.

## Table of Contents

  1. [Parameters](#function-params)
  1. [Hoisting](#hoisting)
  1. [Conditional Expressions & Equality](#conditional-expressions--equality)
  1. [Function Naming](#function-naming)
  1. [Naming Convention](#naming-convention)
  1. [Drupal](#drupal)
    1. [Namespacing](#namespacing)
    1. [Behaviors](#behaviors)
  1. [Property Existence](#property-existence)
  1. [Docs & Comments](#docs-comments)


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

Variables only used in specific code sections (e.g., as a loop index or counter) do not need to be declared at the top of their scope.

> If a particular identifier has been declared var once or more anywhere in a function body(*), then all use of that identifier in the block will be referring to the local variable.
> [Stackoverflow](http://stackoverflow.com/a/3685090/417839).

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

Conditional statements with mulitple clauses including operators can be hard to skim, consider using explicit parenthesis or clear variables.

```javascript
if (typeof myObj.myVar === 'string' && counter >= maxCount && failSafe !== true) {
  // BAD: Takes a moment to realize what's going on.
}
```

```javascript
while (people <= threshold && todoItems >= people) {
  // FINE: Short and clear.
}
```

```javascript
while ((people <= threshold) && (todoItems >= people) && (mySession.active === true)) {
  // HANDY: Helpful to read quickly.
}
```

```javascript
var validList = (typeof myObj.myVar === 'string'),
    active = checkSession(myUserObj, 'status');

if (validList && counter.length && active) {
  // GOOD: So obvious!
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

## Function Naming

AirBnb's style guide says:

> Name your functions. This is helpful for stack traces.

```javascript
// bad
var log = function(msg) {
  console.log(msg);
};

// good
var log = function log(msg) {
  console.log(msg);
};
```

**However**, in Chrome devtools, this is no longer necessary. While debugging (in stack traces, etc.) function names are now inferred from the variable names or object property names they're assigned to.

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


## Drupal

### Namespacing
Use camelcase names for Drupal settings and behaviors.
```javascript
Drupal.settings.myModule.mySetting
Drupal.behaviors.myModuleBehavior
```

You can shorten an unwieldy module name if it's interally custom and a collision is unlikely.
```javascript
// /sites/all/modules/custom/rather_long_module_name/js/long-module.js
Drupal.settings.longModule.mySetting
```

### Behaviors
See [Drupal.behave](https://github.com/tableau-mkt/behave)


## Property Existence

- `myObject.hasOwnProperty(property)` — ignore inherited properties
- `myProperty in myObject` — check if object has property, including inherited properties.
- `myObject.myProperty` or `myObject[property]` — shortest, preferred. NB: `0` is falsy.

**[⬆ back to top](#table-of-contents)**


## Docs & Comments

### Doc Blocks
You should always strive for super readable and parse-able doc blocks. Make developers, IDEs, and documentation generators happy.  Here are some basic requirements...
```javascript
/**
  * Description of function.
  *
  * Longer description with more details or examples is occasionally required.
  *
  * @todo Something to change later, ticket number is nice #123.
  *
  * @param {type} name
  *   Description of variable, often unnecessary.
  * @param {type} var
  *
  * @return {type}
  */
function myFunc () {
```

### Comments
You should write code comments that are concise, explicit, and reasonably grammatically correct (sentence fragments are ok).  Put a space after the comment mark, start with a capital, and end with a period.

You should probably not have more than 4-5 lines without explanation. Omit unnecessary words like "this code..." or "here is the place where...", this could be said about every comment.

**Examples:**

`// Retrieves data from the myServer API.`

`// Load person record via utility library.`

**[⬆ back to top](#table-of-contents)**

## Contributors

  - [Tasty Nerd Tapas](https://twitter.com/nerdtapas)

# };
