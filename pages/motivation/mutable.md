---
level: 2
hideInToc: true
---

# Mutable object

Date's setters modify the instance and can lead to unexpected bugs

<v-click>

Example:
```js
const date = new Date();

const getFirstDay = (dateInstance) => {
  dateInstance.setMonth(0);
  dateInstance.setDate(1);
  return dateInstance;
};

const date1 = getFirstDay(date);
console.log(date);
console.log(date1);
```
</v-click>