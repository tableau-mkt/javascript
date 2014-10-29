# Tableau Mrktg JavaScript Extended Style Guide () {

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
  // No way,
  // Jose.
}
else {
  // This will definitely happen.
  // Yulp.
}
```

  - Conditional statement clauses that only contain one line of executed code may be placed on one line. However, consistency should preceed space savings.

```javascript
if (false) { console.log('not likely'); }
else { console.log('For sure'); }
```

  - For more information see [Truth Equality and JavaScript](http://javascriptweblog.wordpress.com/2011/02/07/truth-equality-and-javascript/#more-2108) by Angus Croll

**[⬆ back to top](#table-of-contents)**

## The JavaScript Style Guide Guide

  - [Reference](https://github.com/tableau-mkt/www7/javascript)

## Contributors

  - [Tasty Nerd Tapas](https://twitter.com/nerdtapas)


## License

(The MIT License)

Copyright (c) 2014 Tableau Software

Permission is hereby granted, free of charge, to any person obtaining
a copy of this software and associated documentation files (the
'Software'), to deal in the Software without restriction, including
without limitation the rights to use, copy, modify, merge, publish,
distribute, sublicense, and/or sell copies of the Software, and to
permit persons to whom the Software is furnished to do so, subject to
the following conditions:

The above copyright notice and this permission notice shall be
included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED 'AS IS', WITHOUT WARRANTY OF ANY KIND,
EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF
MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT.
IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY
CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT,
TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE
SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.

**[⬆ back to top](#table-of-contents)**

# };
