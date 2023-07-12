---
level: 2
---
# Temporal string representation

All Temporal types have a string representation for persistence and interoperability
<v-click>

<div class="flex justify-center">
  <img src="https://tc39.es/proposal-temporal/docs/persistence-model.svg" class="h-60"/>
</div>

</v-click>

<v-click>

Example:
```js
const now = Temporal.Now.zonedDateTimeISO();
console.log(now.toString); // '2023-07-09T21:31:47.689073656+07:00[Asia/Saigon]'
```

</v-click>

