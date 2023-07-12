<script setup lang="ts">
import { Temporal, toTemporalInstant } from '@js-temporal/polyfill';
import dayjs from 'dayjs';
import relativeTime from 'dayjs/plugin/relativeTime';
import advancedFormat from 'dayjs/plugin/advancedFormat';
import customParseFormat from 'dayjs/plugin/customParseFormat';
import utc from 'dayjs/plugin/utc';
import timezone from 'dayjs/plugin/timezone';
import * as luxon from 'luxon';
import * as dateFNS from 'date-fns';

Date.prototype['toTemporalInstant'] = toTemporalInstant;
window['Temporal'] = Temporal;

dayjs.extend(relativeTime);
dayjs.extend(advancedFormat);
dayjs.extend(customParseFormat);
dayjs.extend(utc);
dayjs.extend(timezone);
window['dayjs'] = dayjs;

window['luxon'] = luxon;

window['dateFNS'] = dateFNS;


console.log('Inited Temporal, day.js, Luxon and date-fns');
</script>

<template>
  <div class="hidden">
  </div>
</template>
