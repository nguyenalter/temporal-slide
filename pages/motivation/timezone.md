---
level: 2
hideInToc: true
---

# Lack of support for timezone

Date object lacks of timezone related APIs
<v-click>

Use case: We want to implement a timezone dropdown for users to change their timezone setting
<div class="flex justify-center">
  <img src="/slack-tz.png" class="h-60"/>
</div>
</v-click>

<v-click>

Problem 1: How to get a list of available timezones?
</v-click>

<v-click>

We can not solve this problem using Date built-in methods
</v-click>

<v-click>

Solution: `const timezoneList = Intl.supportedValuesOf('timeZone');`
</v-click>


---
level: 3
hideInToc: true
---

Problem 2: How to get the UTC offset of each timezone in the list?

Example: Get UTC offset of `America/New_York` at the moment

<v-click>

We can not solve this problem using Date built-in methods
</v-click>

<v-click>

Solution:

```js
const getUTCOffset = (timeZone) => {
  const formattedParts = Intl.DateTimeFormat('fr', {
    timeZoneName: 'short',
    timeZone,
  }).formatToParts();
  const utcOffset = formattedParts.find((part) => part.type === 'timeZoneName');
  return utcOffset.value;
};

getUTCOffset(`America/New_York`);
```
</v-click>

