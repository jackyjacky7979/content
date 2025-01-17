---
title: if...else
slug: Web/JavaScript/Reference/Statements/if...else
tags:
  - JavaScript
  - Language feature
  - Reference
  - Statement
  - else
  - if
browser-compat: javascript.statements.if_else
---
{{jsSidebar("Statements")}}

The **`if`** statement executes a
statement if a specified condition is {{Glossary("truthy")}}. If the condition is
{{Glossary("falsy")}}, another statement can be executed.

{{EmbedInteractiveExample("pages/js/statement-ifelse.html")}}

## Syntax

```js
if (condition) {
   statement1
} else {
   statement2
}
```

- `condition`
  - : An [expression](/en-US/docs/Web/JavaScript/Guide/Expressions_and_Operators#expressions)
    that is considered to be either {{Glossary("truthy")}} or {{Glossary("falsy")}}.
- `statement1`
  - : Statement that is executed if _condition_ is {{Glossary("truthy")}}. Can be
    any statement, including further nested `if` statements. To execute
    multiple statements, use a [block](/en-US/docs/Web/JavaScript/Reference/Statements/block) statement
    (`{ /* ... */ }`) to group those statements. To execute no statements, use an [empty](/en-US/docs/Web/JavaScript/Reference/Statements/Empty) statement.
- `statement2`
  - : Statement that is executed if `condition` is
    {{Glossary("falsy")}} and the `else` clause exists. Can be any statement,
    including block statements and further nested `if` statements.

## Description

Multiple `if...else` statements can be nested to create an
`else if` clause. Note that there is no `elseif` (in one word)
keyword in JavaScript.

```js
if (condition1)
  statement1
else if (condition2)
  statement2
else if (condition3)
  statement3
...
else
  statementN
```

To see how this works, this is how it would look if the nesting were properly indented:

```js
if (condition1)
  statement1
else
  if (condition2)
    statement2
  else
    if (condition3)
...
```

To execute multiple statements within a clause, use a block statement
(`{ /* ... */ }`) to group those statements. In general, it is a good practice to
always use block statements, especially in code involving nested `if`
statements:

```js
if (condition) {
  statements1
} else {
  statements2
}
```

Do not confuse the primitive Boolean values `true` and `false`
with truthiness or falsiness of the {{jsxref("Global_Objects/Boolean", "Boolean")}}
object. Any value that is not `false`, `undefined`,
`null`, `0`, `-0`, `NaN`, or the empty
string (`""`), and any object, including a Boolean object whose value is
`false`, is considered {{Glossary("truthy")}} when used as the condition. For
example:

```js
const b = new Boolean(false);
if (b) // this condition is truthy
```

## Examples

### Using if...else

```js
if (cipher_char === from_char) {
  result = result + to_char;
  x++;
} else {
  result = result + clear_char;
}
```

### Using else if

Note that there is no `elseif` syntax in JavaScript. However, you can write
it with a space between `else` and `if`:

```js
if (x > 50) {
  /* do something */
} else if (x > 5) {
  /* do something */
} else {
  /* do something */
}
```

### Using an assignment as a condition

You should almost never have an `if...else` with an assignment like "`x = y`" as a condition:

```js example-bad
if (x = y) {
  /* do something */
}
```

However, in the rare case you find yourself wanting to do something like that, the [`while`](/en-US/docs/Web/JavaScript/Reference/Statements/while) documentation has a [Using an assignment as a condition](/en-US/docs/Web/JavaScript/Reference/Statements/while#using_an_assignment_as_a_condition) section with an example showing a general best-practice syntax you should know about and follow.

## Specifications

{{Specifications}}

## Browser compatibility

{{Compat}}

## See also

- {{jsxref("Statements/block", "block")}}
- {{jsxref("Statements/switch", "switch")}}
- [Conditional operator](/en-US/docs/Web/JavaScript/Reference/Operators/Conditional_Operator)
