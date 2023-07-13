---
level: 2
hideInToc: true
---

# Convert user timezone

How to build a timezone dropdown to allow the user to manually adjust their timezone

<div class="flex justify-center">
  <img src="/timezone-dropdown.png" class="h-80"/>
</div>

- Assumed that we already have the dropdown
- The user wants to change their timezone from `Asia/Ho_Chi_Minh` to `America/New_York`

---
level: 3
hideInToc: true
---

# No library

```js
const currentDate = '2023-07-07T19:00:00.000+07:00';
const date = new Date(currentDate);

// use Intl API
const options = {
  year: 'numeric',
  month: 'numeric',
  day: 'numeric',
  hour: 'numeric',
  minute: 'numeric',
  second: 'numeric',
  timeZone: 'America/New_York',
  timeZoneName: 'long',
};

new Intl.DateTimeFormat('en-CA', options).format(date);
// 2023-07-07, 8:00:00 a.m. Eastern Daylight Saving Time
```

---
level: 3
hideInToc: true
---

# day.js

```js
const currentDate = '2023-07-07T19:00:00.000+07:00';

dayjs(currentDate).tz('America/New_York').format();
// 2023-07-07T08:00:00-04:00
```

---
level: 3
hideInToc: true
---

# Luxon

```js
const currentDate = '2023-07-07T19:00:00.000+07:00';
const dt = luxon.DateTime.fromISO(currentDate);

dt.setZone('America/New_York').toISO();
// 2023-07-07T08:00:00.000-04:00
```

---
level: 3
hideInToc: true
---

# date-fns

```js
import { formatInTimeZone } from 'date-fns-tz';

const currentDate = '2023-07-07T19:00:00.000+07:00';
const date = new Date(currentDate);

formatInTimeZone(date, 'America/New_York', "yyyy-MM-dd'T'HH:mm:ssXXX");
// 2023-07-07 08:00:00-04:00
```

---
level: 3
hideInToc: true
---

# Temporal

```js
const currentDate = '2023-07-07T19:00:00.000+07:00';
const instant = Temporal.Instant.from(currentDate);
const zdt = instant.toZonedDateTimeISO('America/New_York');
zdt.toString();
// '2023-07-07T08:00:00-04:00[America/New_York]'
```

