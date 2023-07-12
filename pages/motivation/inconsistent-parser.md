---
level: 2
hideInToc: true
---

# Inconsistent parser

The parser may give a different output depending on the input string and the browser that implements the parse method


<v-click>

Example 1: Parse a date without and with time

<div class="flex justify-between gap-x-3">
  <div>
    <span>Without specify the time</span>
    <img src="/date-no-time.png"/>
  </div>
  <div>
    <span>Specify the time</span>
    <img src="/date-time.png"/>
  </div>
</div>

</v-click>

<v-click>

Example 2: Parse an out of bound date, dash separated `'2023-02-30'`
<div class="flex justify-between gap-x-3">
  <div>
    <span>Firefox</span>
    <img src="/invalid-date-firefox.png"/>
  </div>
  <div>
    <span>Chrome</span>
    <img src="/invalid-date-chrome.png"/>
  </div>
  <div>
    <span>Safari</span>
    <img src="/invalid-date-safari.png"/>
  </div>
</div>
</v-click>

<v-click>

Example 3: Parse an out of bound date, slash separated `'02/30/2023'`
<div class="flex justify-between gap-x-3">
  <div>
    <span>Firefox</span>
    <img src="/invalid-date-firefox2.png"/>
  </div>
  <div>
    <span>Chrome</span>
    <img src="/invalid-date-chrome2.png"/>
  </div>
  <div>
    <span>Safari</span>
    <img src="/invalid-date-safari2.png"/>
  </div>
</div>
</v-click>

---
level: 3
hideInToc: true
---

Example 4: Parse an date, comma separated `'2023,1,1'`

<div class="flex justify-between gap-x-3">
  <div>
    <span>Firefox</span>
    <img src="/date-comma-firefox.png"/>
  </div>
  <div>
    <span>Chrome</span>
    <img src="/date-comma-chrome.png"/>
  </div>
  <div>
    <span>Safari</span>
    <img src="/date-comma-safari.png"/>
  </div>
</div>

<v-click>

Example 5: Parse zero date `'0'`

<div class="flex justify-between gap-x-3">
  <div>
    <span>Firefox</span>
    <img src="/date-zero-firefox.png"/>
  </div>
  <div>
    <span>Chrome</span>
    <img src="/date-zero-chrome.png"/>
  </div>
  <div>
    <span>Safari</span>
    <img src="/date-zero-safari.png"/>
  </div>
</div>
</v-click>

<v-click>

Example 6: Parse a date, space separated `'07 14 2023'`

<div class="flex justify-between gap-x-3">
  <div>
    <span>Firefox</span>
    <img src="/date-space-firefox.png"/>
  </div>
  <div>
    <span>Chrome</span>
    <img src="/date-space-chrome.png"/>
  </div>
  <div>
    <span>Safari</span>
    <img src="/date-space-safari.png"/>
  </div>
</div>
</v-click>
