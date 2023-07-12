---
level: 2
---
# Temporal objects

Temporal provides 11 objects to work with Date/Time problems

<div class="flex justify-center">
  <img src="https://tc39.es/proposal-temporal/docs/object-model.svg" class="h-50"/>
</div>

<v-click>

- The object names that start with 'Plain' do not have an associated time zone. Example:
```js
Temporal.PlainDate.from('2023-07-14');
Temporal.PlainMonthDay.from('07-14');
Temporal.PlainTime.from('15:00');
```
</v-click>

<v-click>

- To retrieve the local date time from an instant, we must convert it to other types. Example:
```js
const tz = Temporal.TimeZone.from('Asia/Ho_Chi_Minh');
const now = Temporal.Now.instant();
tz.getPlainDateTimeFor(now).toString(); // 2023-07-13T02:32:31.851327516
```
</v-click>