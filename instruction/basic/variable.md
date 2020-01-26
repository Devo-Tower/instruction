# Variables

Variables are a way to store information for later use.  A variable has a name and a value.  
A variable's name stays the same, but its value can be updated.  It's the exact same as a math variable.
So as part of a basic math equation, you may write:

```
a = 3
b = 5
c = a + b = 8
```

In Javascript, you'd write:

```javascript
let a = 3;
let b = 5;
let c = a + b;
```

## Using Variables

When you first use a variable, you have to **initialize** or **declare** it.  This lets Javascript know that you are about to give a variable a name
and a default value.

### Initializing / Declaring Variables

To **initialize** a variable, you have to explicitely give it a default value:

```javascript
let myVariable = 3;
```

In this example, the variable is named `myVariable` and has the value `3`.

To **declare** a variable, you do not need to give it a default value.  In this case, the default value will be `null`, meaning no value.

```javascript
let myVariable;
```

> Note that programmers will often use the term "declare" instead of "initialize" since when you "initialize" a variable, you are also "declaring" it (aka, giving it a name).

### Reassigning Variables

You can also change the value of a initialized/declared variable later.  
Note that when you change the variable's value, you should not use `let` again: `let` is only used when you first name it:

```javascript
let myVariable = 3;
myVariable = 5;
```

In the example above, the final value of the variable is `5`.

## Other Variables

### Const

> This is an advanced concept, if it's too difficult to comprehend, just ALWAYS use `let` and you'll be okay.

In Javascript, there are actually two ways to declare a variable (ex: `myVariable`):

* `let myVariable;`
* `const myVariable;`

You can also give a variable an initial value (ex: `"hello world"`):

* `let myVariable = "hello world";`
* `const myVariable = "hello world";`

This is called initializing a variable.

The difference between `let` and `const` is that `const` variables cannot change their value: they are constant;
whereas the value of a `let` variable can be changed.  For example:

```javascript
let myVariable = "hello world";
myVariable = "something else";
```
is allowed, but:
```javascript
const myVariable = "hello world";
myVariable = "something else";
```
will cause an error.

Note that if the value is an [array](./array.md) or [JSON object](./json.md) then you can still alter the variable through
dot notation (`.`), even if the variable is a `const`.  For example, the following is allowed:
```javascript
const myVariable = { "name": "Bob Jones"};
myVariable.name = "Sally Jones";
```

> Best practice is that, by default, you should always use `const` unless `let` is explicitely needed.  If you're
> unsure if `let` is needed for a variable, just start with `const`, and if you ever write `myVariable = `, anywhere
> else in the code, you know you should switch it from `const` to `let`.

### Var

On some examples online, you may see `var` used instead of `let` or `const`; `var` is an old way to say `let` or `const` and it has
some [nasty unexpected side effects](https://scotch.io/tutorials/understanding-hoisting-in-javascript).  Avoid using `var`.