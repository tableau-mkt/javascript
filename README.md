# JavaScript Style Guide, extended () {

*An approach to JavaScript beyond reasonable*
Don't be afraid to make rules for: readability, future-proofing, and elegance.

## Table of Contents

  1. [Parameters](#function-params)
  1. [Hoisting](#hoisting)
  1. [Conditional Expressions & Equality](#conditional-expressions--equality)
  1. [Naming Convention](#naming-convention)
  1. [Drupal](#drupal)
    1. [Namespacing](#namespacing)
    1. [Behaviors](#behaviors)


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


## Drupal

## Namespacing
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

## Behaviors
See [Drupal.behave](https://github.com/tableau-mkt/behave)


## Contributors

  - [Tasty Nerd Tapas](https://twitter.com/nerdtapas)

# };
