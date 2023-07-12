---
level: 2
hideInToc: true
---

# Inconsistent parser

The parser may give a different output depending on the input string and the browser that implements the parse method

<v-click>

Example
```js
const date1 = new Date('2023-06-05');
const date2 = new Date('2023-06-05T00:00');
```
</v-click>

<v-click>

Comparison
```js
console.log(date1 - date2 === 0);

```
</v-click>

<v-click>

Why?
```js
console.log(date1.toISOString());
console.log(date2.toISOString());
```
</v-click>