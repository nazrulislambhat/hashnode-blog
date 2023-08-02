---
title: "VAR vs LET vs CONST in JavaScript"
seoTitle: "VAR vs LET vs CONST - Understanding the Difference"
seoDescription: "Confused about which JavaScript variable declaration to use? Learn the key differences between VAR, LET, and CONST, and make informed decisions for cleaner"
datePublished: Wed Aug 02 2023 06:42:58 GMT+0000 (Coordinated Universal Time)
cuid: clktd2tqm000609mediae64k6
slug: var-vs-let-vs-const-in-javascript
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1690958387380/09010ea2-5cf3-44a9-a4c6-bfc07fb2acf2.jpeg
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1690958519601/ff30ab9f-f988-4586-bd09-3b468733936f.jpeg
tags: variables, javascript, const, let

---

In ES6, some new features were introduced, including `let` and `const`, which offer alternatives for declaring variables. You might be wondering how they differ from the traditional `var` that we've been using. If you're not clear about this yet, don't worry – this article will help you understand it all.

We'll explore the differences between `var`, `let`, and `const` with respect to their scope, usage, and hoisting. As you read on, pay attention to the key distinctions I'll be pointing out.

Let's take a look at `var` first.

Before ES6, `var` was the primary way to declare variables. However, it comes with some issues. This is why new ways of declaring variables were introduced. Let's dive deeper into `var` before we discuss those problems.

The scope of `var` determines where the variables are accessible. When a `var` variable is declared outside a function, it is globally scoped. This means the variable can be used throughout the entire window.

On the other hand, when a `var` variable is declared within a function, it becomes function-scoped. This means it is only accessible within that specific function.

For example:

```javascript
var greeter = "hey hi";

function newFunction() {
    var hello = "hello";
}
```

In this case, `greeter` is globally scoped, and `hello` is function-scoped. So, if we try to access `hello` outside the function, we'll get an error because it's not defined in that context.

One thing to note is that `var` variables can be re-declared and updated within their scope without any errors. For example:

```javascript
var greeter = "hey hi";
var greeter = "say Hello instead"; // No error
```

Another important concept related to `var` is hoisting. In JavaScript, variables declared with `var` are hoisted to the top of their scope and initialized with the value `undefined`. For example:

```javascript
console.log(greeter); // undefined
var greeter = "say hello";
```

The problem with `var` arises when we unintentionally re-declare a variable within the same scope, leading to unexpected behavior and potential bugs in our code.

Now, let's discuss `let`.

With ES6, `let` became the preferred way of declaring variables because it addressed the issues associated with `var`. Here's why:

`let` is block-scoped, which means it is only accessible within the block (a chunk of code enclosed in curly braces) where it is declared. For example:

```javascript
let greeting = "say Hi";
let times = 4;

if (times > 3) {
    let hello = "say Hello instead";
    console.log(hello); // "say Hello instead"
}
console.log(hello); // Error: hello is not defined
```

Unlike `var`, a variable declared with `let` cannot be re-declared within the same scope. However, it can be updated with a new value. For example:

```javascript
let greeting = "say Hi";
greeting = "say Hello instead"; // No error
```

Also, if you declare a variable with `let` in different scopes, they will be treated as separate variables. This is why `let` is considered better than `var` because it prevents accidental re-declarations within the same scope.

As with `var`, `let` declarations are also hoisted to the top of their scope. However, unlike `var`, `let` variables are not initialized, so trying to use a `let` variable before declaring it will result in a Reference Error.

Finally, let's explore `const`.

Variables declared with `const` maintain constant values, meaning their values cannot be changed or re-declared. Like `let`, `const` declarations are block-scoped, so they are only accessible within the block where they are declared.

For example:

```javascript
const greeting = "say Hi";
greeting = "say Hello instead"; // Error: Assignment to constant variable
```

The `const` keyword ensures that once a value is assigned to a variable, it cannot be changed throughout its scope. Every `const` declaration must be initialized at the time of declaration.

However, there's a special case with objects declared using `const`. While the variable itself cannot be updated or re-declared, the properties of the object can be changed. For example:

```javascript
const greeting = {
    message: "say Hi",
    times: 4
}

greeting.message = "say Hello instead"; // This is allowed and updates the value
```

To summarize the key differences:

* `var` is globally or function-scoped, while `let` and `const` are block-scoped.
    
* `var` variables can be updated and re-declared within their scope, while `let` variables can be updated but not re-declared, and `const` variables can neither be updated nor re-declared.
    
* All three are hoisted to the top of their scope, but `var` variables are initialized as `undefined`, while `let` and `const` variables are not initialized.
    
* `const` must be initialized during declaration, and once assigned, its value cannot be changed. However, properties of a `const` object can be modified.
    

[Image Credit](https://www.linkedin.com/pulse/let-vs-var-const-difference-between-javascript-manik-bajaj/)