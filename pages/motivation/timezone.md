---
level: 2
hideInToc: true
---

# Lack of support for timezone

Date object lacks of timezone related APIs
<v-click>

Problem 1: Now is 2023/07/14 at 15:00 in Ho Chi Minh city. What time is it in New York?

</v-click>

<v-click>

Solution:
- Date does not provide a built-in method to convert or display a different timezone rather than local time and UTC time
- However, Date has a `toLocaleString` method to take advantage of the Intl API.
</v-click>

<v-click>

```js
const now = new Date('2023-07-14T15:00'); // local time
now.toLocaleString('en-GB', { timeZone: 'America/New_York' });
// 14/07/2023, 04:00:00
```
</v-click>

---
level: 3
hideInToc: true
---

Problem 2: We want to convert a local date to a date with UTC offset equals to +02:00

<v-click>

Solution:
- We can apply the same approach as above if only we have the `timeZone` string
- Let's choose Europe/Berlin because it's using UTC +02:00 offset

```js
const date = new Date('2023-07-14T15:00'); // UTC +07:00
date.toLocaleString('en-GB', { timeZone: 'Europe/Berlin' }); // UTC +02:00
// 14/07/2023, 10:00:00
```
</v-click>

<v-click>

The solution above looks good, let's input another date
</v-click>

<v-click>

```js
const date = new Date('2023-11-14T15:00'); // UTC +07:00
date.toLocaleString('en-GB', { timeZone: 'Europe/Berlin' });
```
</v-click>
