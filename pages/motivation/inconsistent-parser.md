---
level: 2
hideInToc: true
---

# Inconsistent parser

Problem 1: Different browsers parse the same string give different result

<v-click>

Example 1: Parse an invalid date
```js
Date.parse('2023-02-30');
```
</v-click>

<v-click>

<p>Result:</p>
<img src="/firefox.svg" class="h-10">
```js
NaN
```
<br>
<img src="/chrome.svg" class="h-10">
```js
1677715200000
```
<br>
<img src="/safari.svg" class="h-10">

```js
NaN
```

</v-click>

---
level: 3
hideInToc: true
---

Example 2: Parse a date, comma separated
```js
Date.parse('2023,1,1');
```

<v-click>

<p>Result:</p>
<img src="/firefox.svg" class="h-10">
```js
1672506000000
```
<br>
<img src="/chrome.svg" class="h-10">
```js
1672506000000
```
<br>
<img src="/safari.svg" class="h-10">

```js
NaN
```
</v-click>

---
level: 3
hideInToc: true
---
Problem 2: Date does not provide a way to specify the parse format -> uncontrolled the result

<v-click>

Example 1: Parse a date in `YYYY-MM-DDThh:mm` format
```js
new Date('2023-07-14T00:00').toISOString();
// '2023-07-13T17:00:00.000Z'
```
</v-click>

<v-click>

Example 2: Parse a date in `YYYY-MM-DD` format
```js
new Date('2023-07-14').toISOString();
// '2023-07-14T00:00:00.000Z'
```
</v-click>

<v-click>

Example 3: Parse a date in `YYYY/MM/DD` format
```js
new Date('2023/07/14').toISOString();
// '2023-07-13T17:00:00.000Z'
```
</v-click>


---
level: 3
hideInToc: true
---

Example 4: Parse a date in `MM DD YYYY` format
```js
Date.parse('07 14 2023');
```

<v-click>

<p>Result:</p>
<img src="/firefox.svg" class="h-10">
```js
1689267600000
```
<br>
<img src="/chrome.svg" class="h-10">
```js
1689267600000
```
<br>
<img src="/safari.svg" class="h-10">

```js
NaN
```
</v-click>

---
level: 3
hideInToc: true
---

Example 5: Parse a zero string
```js
Date.parse('0');
```

<v-click>

<p>Result:</p>
<img src="/firefox.svg" class="h-10">
```js
NaN
```
<br>
<img src="/chrome.svg" class="h-10">
```js
946659600000
```
<br>
<img src="/safari.svg" class="h-10">

```js
-62167219200000
```
</v-click>
