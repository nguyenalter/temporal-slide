<script setup lang="ts">
import { Temporal, toTemporalInstant } from '@js-temporal/polyfill';
import dayjs from 'dayjs';
import duration from 'dayjs/plugin/duration';
import relativeTime from 'dayjs/plugin/relativeTime';
import advancedFormat from 'dayjs/plugin/advancedFormat';
import customParseFormat from 'dayjs/plugin/customParseFormat';
import utc from 'dayjs/plugin/utc';
import timezone from 'dayjs/plugin/timezone';
import * as luxon from 'luxon';
import * as dateFNS from 'date-fns';
import * as dateFNSTimezone from 'date-fns-tz';

Date.prototype['toTemporalInstant'] = toTemporalInstant;
window['Temporal'] = Temporal;

dayjs.extend(duration)
dayjs.extend(relativeTime);
dayjs.extend(advancedFormat);
dayjs.extend(customParseFormat);
dayjs.extend(utc);
dayjs.extend(timezone);
window['dayjs'] = dayjs;

window['luxon'] = luxon;

window['dateFNS'] = dateFNS;
window['dateFNSTimezone'] = dateFNSTimezone;


console.log('Inited Temporal, day.js, Luxon and date-fns');
</script>

<template>
  <div class="hidden">
  </div>
</template>


<style>
.slidev-layout h1+p {
  opacity: 1 !important;
}

.slidev-page-2, .slidev-page-3, .slidev-page-4 {
  font-size: 28px !important;
  line-height: normal !important;
}
.slidev-page-3 h1+p, .slidev-page-4 h1+p {
  margin-top: 40px !important;
}
tr > td:nth-child(1), tr > th:nth-child(1) {
  background-color: #647B5A;
}
</style>