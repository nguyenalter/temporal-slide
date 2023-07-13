---
level: 2
hideInToc: true
---
# String representation

All Temporal types have a string representation for persistence and interoperability

<div class="flex justify-center">
  <img src="https://tc39.es/proposal-temporal/docs/persistence-model.svg" class="h-50"/>
</div>


<v-click>

=> This is to ensure that Temporal parses a Date string with a strict rule

</v-click>

<v-click>

Example:
```js
instant = Temporal.Instant.from('2019-03-30T01:45:00+01:00[Europe/Berlin]'); // valid
instant = Temporal.Instant.from('2019-03-30T01:45+01:00'); // valid
instant = Temporal.Instant.from('2019-03-30T00:45Z'); // valid
instant = Temporal.Instant.from('2019-03-30'); // => error, no time
instant = Temporal.Instant.from('2019-03-30T01:45'); // => error, no UTC offset
```
</v-click>

