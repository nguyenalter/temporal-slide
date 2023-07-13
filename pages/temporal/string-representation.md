---
level: 2
hideInToc: true
---
# String representation

All Temporal types have a string representation for persistence and interoperability

<div class="flex justify-center">
  <img src="https://tc39.es/proposal-temporal/docs/persistence-model.svg" class="h-60"/>
</div>


<v-click>

Example:
```js
const now = Temporal.Now.zonedDateTimeISO();
console.log(now.toString()); // '2023-07-13T02:34:58.161492801+07:00[Asia/Saigon]'
```

</v-click>

