---
level: 2
hideInToc: true
---
# What is Temporal?

Temporal is a global JavaScript Object that acts as a top-level namespace to provide a modern Date/Time APIs to the ECMAScript language

<v-click>

Example:
- Get the current date and display as a iso8601 string
```js
Temporal.Now.instant().toString();
// 2023-07-12T18:44:11.033433231Z
```
</v-click>

<v-click>

- Get total of days in 2022 and 2023 in Chinese calendar
```js
const cal = Temporal.Calendar.from('chinese');
cal.daysInYear('2023-01-21'); // 355
cal.daysInYear('2023-01-22'); // 384
```
</v-click>

<v-click>

- Get the current UTC offset of Europe/Berlin
```js
const now = Temporal.Now.instant();
const tz = Temporal.TimeZone.from('Europe/Berlin');
tz.getOffsetStringFor(now);
// '+02:00'
```
</v-click>
