---
level: 2
---
# Temporal Object relationship

Temporal provides 11 objects to work with Date/Time problems
<v-click>

<div class="flex justify-center">
  <img src="https://tc39.es/proposal-temporal/docs/object-model.svg" class="h-60"/>
</div>

</v-click>

<v-click>

Example:
```js
const now1 = Temporal.Now.instant();
const now2 = Temporal.Instant.from(new Date().toISOString());
```

</v-click>

