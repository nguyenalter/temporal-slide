---
level: 2
hideInToc: true
---

# Get the duration between 2 dates

Problem: My birthday is October 10. How many days from now until my next birthday? Today is 2023/07/07

---
level: 3
hideInToc: true
---

# No library

```js
const currentDate = '2023-07-07T07:00:00+07:00';
const nextBirthday = '2023-10-03T07:00:00+07:00';

const date = new Date(currentDate);
const birthdayDate = new Date(nextBirthday);

const milisecondsInADay = 1000*60*60*24;
const totalOfDays = (birthdayDate - date) / milisecondsInADay;
```

---
level: 3
hideInToc: true
---

# day.js

```js
const currentDate = '2023-07-07T07:00:00+07:00';
const nextBirthday = '2023-10-03T07:00:00+07:00';

const dayjsBirthday = dayjs(nextBirthday);
const dayjsToday = dayjs(currentDate);

const duration = dayjs.duration(dayjsBirthday.diff(dayjsToday));
duration.asDays();
```

---
level: 3
hideInToc: true
---

# Luxon

```js
const currentDate = '2023-07-07T07:00:00+07:00';
const nextBirthday = '2023-10-03T07:00:00+07:00';

const date = new Date(currentDate);
const birthdayDate = new Date(nextBirthday);

const luxonDuration = luxon.DurationfromMillis(birthdayDate - date);
luxonDuration.as('days');
```

---
level: 3
hideInToc: true
---

# date-fns

```js
import { differenceInDays} from 'date-fns';

const currentDate = '2023-07-07T07:00:00+07:00';
const nextBirthday = '2023-10-03T07:00:00+07:00';

const date = new Date(currentDate);
const birthdayDate = new Date(nextBirthday);

differenceInDays(birthdayDate, date);
```

---
level: 3
hideInToc: true
---

# Temporal

```js
const currentDate = '2023-07-07T07:00:00+07:00';
const nextBirthday = '2023-10-03T07:00:00+07:00';

const instant = Temporal.Instant.from(currentDate);
const birthdayInstant = Temporal.Instant.from(nextBirthday);
const temporalDuration = instant.until(birthdayInstant);
temporalDuration.total('day');
```