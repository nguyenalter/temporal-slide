---
level: 2
hideInToc: true
---

# Format Date Time

How to show the Date Time like this picture to the end user?

<div class="flex justify-center">
  <img src="/dbdiagram-version-history.png" class="h-20"/>
</div>

---
level: 3
hideInToc: true
---

# No library

```js
const createdAt = '2023-06-20T18:59:53.224Z';
const date = new Date(createdAt);

const months = ['January', 'February', 'March', 'April', 'May', 'June',
	'July', 'August', 'September', 'October', 'November', 'December'];
const monthIdx = date.getMonth(); // 1
const monthName = months[monthIdx]; // February
const getDayOfMonthWithOrdinal = (day) => {
	switch (day % 10) {
		case 1: return `${day}st`;
		case 2: return `${day}nd`;
		case 3: return `${day}rd`;
		default: return `${day}th`;
	}
};
const year = date.getFullYear(); // 2023
const dayOfMonth = getDayOfMonthWithOrdinal(date.getDate()); // 21st
const time = date.toLocaleTimeString('en-US', { hour:'numeric', minute:'numeric'});
const result = `${monthName} ${dayOfMonth} ${year}, ${time}`;
```

---
level: 3
hideInToc: true
---

# day.js

```js
const createdAt = '2023-06-20T18:59:53.224Z';

dayjs(createdAt).format('MMM Do YYYY, H:mm A'); // need advancedFormat plugin
```

---
level: 3
hideInToc: true
---

# Luxon

```js
const createdAt = '2023-06-20T18:59:53.224Z';

luxon.DateTime.fromISO(createdAt).toFormat(`LLLL '${dayOfMonth}' yyyy, h:mm a`);
```

---
level: 3
hideInToc: true
---

# date-fns

```js
import { format } from 'date-fns';

const createdAt = '2023-06-20T18:59:53.224Z';
const date = new Date(createdAt);

format(date, 'MMMM do yyyy, h:mm a');
```