# Variables and Types

## **Variables**

We can think of variables like containers (or a box) for our data and this data will have a type like number or text.

We declare our variables with the words `var` `let` or `const`

```javascript
// Ways to declare a variable
// `var`, `let`, & `const`

let firstName = 'John';
const lastName = 'Doe';
let age = 30;

//We also can make multi declare.
let firstName, lastName, age
const nome = 'Larissa',
    time = 'Flamengo',
    pais = 'Brasil';
```

### **Naming variables**

We should stick with naming conventions when naming our variables, use only letters, numbers and underscores and dollar sign.

Do not start with a number!

Use the multi-word formatting
```javascript
// Naming Conventions
// - Only letters, numbers, underscores and dollar signs
let letter = 'a'
let number1 = 12
let number_2 = 10


// Multi-Word Formatting
// firstName = camelCase
// first_name = underscore
// FirstName = PascalCase
// firstname = lowercase
let fisrtName = 'Thiago'
let last_name = 'Silva'
let SaldoConta = 2000
let saldosalario = 300
```

## Data Types

**Primitive data types are:** 

- Strings: sequence of characters
- Number: Integer as well as floating
- Boolean: true or false
- Null: suposed to be empty, Intentional absence of value
- Undefined: variable that does not have been defined/assigned

Primitive types are acessed by the stored data (kind of directly).

```javascript
// String
const firstName = 'Sara';

// Number
const age = 30;
const temp = 98.9;

// Boolean
const hasKids = true;

// Null
const aptNumber = null;

// Undefined
// let score;
const score = undefined;

// Symbol
const id = Symbol('id');

// More info on why typeof null == object
// https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/typeof#typeof_null

//  More info on the "function object" type
// https://262.ecma-international.org/5.1/#sec-11.4.3
```

**Reference Types (objects):** 

- Arrays
- Functions
- Object
- Literals

They are acessed by reference in the memory.
```javascript
// Reference Types

const numbers = [1, 2, 3, 4];

const person = {
  name: 'Goku',
};

function sayHello() {
  console.log('Hello');
}

const output = sayHello;
```

## Converting Types
```javascript
let amount = '10';

// Convert string to number
amount = parseInt(amount);
amount = +amount;
amount = Number(amount);

// Convert number to string
amount = amount.toString();
amount = String(amount);

// Convert string to decimal
amount = parseFloat(amount);

// Convert number to boolean
amount = Boolean(amount);

// Ways to get NaN
console.log(Math.sqrt(-1));
console.log(1 + NaN);
console.log(undefined + undefined);
console.log('foo' / 3);
```

## Var x Let x Const

Before ES6 we used var to declare variables, but nowadays it’s not so commonly used anymore as var 
 is function scoped. This means that any variable created with var is available anywhere in the function in which it is defined.

In the example below we declare name in an if statement but we can use it outside the statement.
```javascript
if (true) {
  var name = "Thais"
}
console.log(name)
// Prints: Thais
```

After ES6 we have `let` and `const` that are block scoped which means that they are only available inside the block in which they are defined.

```javascript
if (true) {
  let name = "Thais"
}
console.log(name)
// Prints: / Uncaught ReferenceError: name is not defined

//The way for this code to work should be:
if (true) {
  let name = "Thais"
  console.log(name)
  // Prints: Thais
}
```

Another thing about ``let`` x ``const`` is that with ``let`` we can declare but not initialize it while ``const`` we must always initialize the variable. Also const should never be reassigned.

```javascript
const name = "Thiago" //inicializada
console.log(name)
// Prints: Thiago
name = "Roberta"
// Uncaught TypeError: Assignment to constant variable.
console.log(name)
```

### Null x Undefined

Both `null` and `undefined` mean that there is no value. If a variable is set to `null` or `undefined` it has no value and if a function returns `null` or `undefined` then it is saying it has no value to return.

*These values are actually so similar that they are considered equal when comparing with double equals

```javascript
let a
let b = null

console.log(a)
// undefined
console.log(b)
// null
```

If a variable is `null` then it means the variable has no  value and that it was explicitly set to have no value by the programmer. A variable will never be `null` unless somewhere in the code a programmer set a variable to `null`.

A great example of where `null` is useful is in something  like a find function that queries a database for an entry. If no entry  exists it makes the most sense to return `null` since you are stating that there is no value found.

On the other hand `undefined` means that there is no value  because no value has been set yet. For example, if you create a variable and do not assign it a value then it will be `undefined`.