---
level: 2
hideInToc: true
---

# Lack of utility methods
Utility methods: methods that support format, parse, duration, time before, time after, arithmetic, etc.

Date object provide a limited APIs to get, set, convert and format the Date instance. For example:
- `getDate()`
- `getFullYear()`
- `setMonth()`
- `setHours()`
- `UTC()`
- `toISOString()`

<v-click>

Use case 1: A task must be done in 2 weeks from now. When is the deadline date?
</v-click>

<v-click>

Solution:
```js
const now = new Date(); // 2023-07-12T09:50:04.755Z
const deadline = new Date(now.setDate(now.getDate() + 14));
console.log(now.toISOString()); // 2023-07-26T09:50:04.755Z
console.log(deadline.toISOString()); // 2023-07-26T09:50:04.755Z
```
</v-click>
---
level: 3
hideInToc: true
---

Use case 2: The next Tet (Lunar New Year) is February 10, 2024. How many days until the next Tet?
<v-click>

Solution:
```js
const now = new Date();
const tet = new Date('2024-02-10T00:00+07:00');
const milisecondsInADay = 1000 * 60 * 60 * 24;
const days = (tet - now) / milisecondsInADay;
```

</v-click>

<v-click>

Use case 3: We need to show the version history date in this format
<div class="flex justify-center">
  <img src="/dbdiagram-version-history.png" class="h-20"/>
</div>
</v-click>

<v-click>

Solution:
<div class="flex justify-center">
  <svg version="1.1" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 1062.9218532894329 201.77984777865277" width="531.4609266447164" height="100.88992388932638">
  <!-- svg-source:excalidraw -->
  
  <defs>
    <style class="style-fonts">
      @font-face {
        font-family: "Virgil";
        src: url("https://excalidraw.com/Virgil.woff2");
      }
      @font-face {
        font-family: "Cascadia";
        src: url("https://excalidraw.com/Cascadia.woff2");
      }
    </style>
    
  </defs>
  <rect x="0" y="0" width="1062.9218532894329" height="201.77984777865277" fill="#ffffff"></rect><g stroke-linecap="round" transform="translate(387.65474191497015 10) rotate(0 107 24.5)"><path d="M12.25 0 M12.25 0 C64.3 0, 116.35 0, 201.75 0 M12.25 0 C82.99 0, 153.73 0, 201.75 0 M201.75 0 C209.92 0, 214 4.08, 214 12.25 M201.75 0 C209.92 0, 214 4.08, 214 12.25 M214 12.25 C214 20.91, 214 29.56, 214 36.75 M214 12.25 C214 17.55, 214 22.86, 214 36.75 M214 36.75 C214 44.92, 209.92 49, 201.75 49 M214 36.75 C214 44.92, 209.92 49, 201.75 49 M201.75 49 C129.5 49, 57.26 49, 12.25 49 M201.75 49 C155.91 49, 110.07 49, 12.25 49 M12.25 49 C4.08 49, 0 44.92, 0 36.75 M12.25 49 C4.08 49, 0 44.92, 0 36.75 M0 36.75 C0 31.57, 0 26.38, 0 12.25 M0 36.75 C0 30.73, 0 24.72, 0 12.25 M0 12.25 C0 4.08, 4.08 0, 12.25 0 M0 12.25 C0 4.08, 4.08 0, 12.25 0" stroke="#364fc7" stroke-width="1" fill="none"></path></g><g transform="translate(393.854777010185 17) rotate(0 100.79996490478516 17.5)"><text x="100.79996490478516" y="0" font-family="Virgil, Segoe UI Emoji" font-size="28px" fill="#364fc7" text-anchor="middle" style="white-space: pre;" direction="ltr" dominant-baseline="text-before-edge">custom format</text></g><g stroke-linecap="round" transform="translate(10 139.61471317370524) rotate(0 107 24.5)"><path d="M12.25 0 M12.25 0 C85.1 0, 157.96 0, 201.75 0 M12.25 0 C59.39 0, 106.53 0, 201.75 0 M201.75 0 C209.92 0, 214 4.08, 214 12.25 M201.75 0 C209.92 0, 214 4.08, 214 12.25 M214 12.25 C214 21.57, 214 30.88, 214 36.75 M214 12.25 C214 19.05, 214 25.85, 214 36.75 M214 36.75 C214 44.92, 209.92 49, 201.75 49 M214 36.75 C214 44.92, 209.92 49, 201.75 49 M201.75 49 C160.34 49, 118.92 49, 12.25 49 M201.75 49 C158.32 49, 114.89 49, 12.25 49 M12.25 49 C4.08 49, 0 44.92, 0 36.75 M12.25 49 C4.08 49, 0 44.92, 0 36.75 M0 36.75 C0 29.69, 0 22.62, 0 12.25 M0 36.75 C0 29.87, 0 23, 0 12.25 M0 12.25 C0 4.08, 4.08 0, 12.25 0 M0 12.25 C0 4.08, 4.08 0, 12.25 0" stroke="#364fc7" stroke-width="1" fill="none"></path></g><g transform="translate(39.622032165527344 146.61471317370524) rotate(0 77.37796783447266 17.5)"><text x="77.37796783447266" y="0" font-family="Virgil, Segoe UI Emoji" font-size="28px" fill="#364fc7" text-anchor="middle" style="white-space: pre;" direction="ltr" dominant-baseline="text-before-edge">month name</text></g><g stroke-linecap="round" transform="translate(582.8712678278389 142.77984777865277) rotate(0 107 24.5)"><path d="M12.25 0 M12.25 0 C84.17 0, 156.08 0, 201.75 0 M12.25 0 C82.66 0, 153.08 0, 201.75 0 M201.75 0 C209.92 0, 214 4.08, 214 12.25 M201.75 0 C209.92 0, 214 4.08, 214 12.25 M214 12.25 C214 17.95, 214 23.65, 214 36.75 M214 12.25 C214 19.78, 214 27.31, 214 36.75 M214 36.75 C214 44.92, 209.92 49, 201.75 49 M214 36.75 C214 44.92, 209.92 49, 201.75 49 M201.75 49 C132.11 49, 62.47 49, 12.25 49 M201.75 49 C132.25 49, 62.75 49, 12.25 49 M12.25 49 C4.08 49, 0 44.92, 0 36.75 M12.25 49 C4.08 49, 0 44.92, 0 36.75 M0 36.75 C0 27.67, 0 18.58, 0 12.25 M0 36.75 C0 27.76, 0 18.77, 0 12.25 M0 12.25 C0 4.08, 4.08 0, 12.25 0 M0 12.25 C0 4.08, 4.08 0, 12.25 0" stroke="#364fc7" stroke-width="1" fill="none"></path></g><g transform="translate(660.2892823542061 149.77984777865277) rotate(0 29.581985473632812 17.5)"><text x="29.581985473632812" y="0" font-family="Virgil, Segoe UI Emoji" font-size="28px" fill="#364fc7" text-anchor="middle" style="white-space: pre;" direction="ltr" dominant-baseline="text-before-edge">year</text></g><g stroke-linecap="round" transform="translate(838.9218532894329 141.54983498384172) rotate(0 107 24.5)"><path d="M12.25 0 M12.25 0 C79.08 0, 145.91 0, 201.75 0 M12.25 0 C56.8 0, 101.35 0, 201.75 0 M201.75 0 C209.92 0, 214 4.08, 214 12.25 M201.75 0 C209.92 0, 214 4.08, 214 12.25 M214 12.25 C214 21.38, 214 30.51, 214 36.75 M214 12.25 C214 17.28, 214 22.32, 214 36.75 M214 36.75 C214 44.92, 209.92 49, 201.75 49 M214 36.75 C214 44.92, 209.92 49, 201.75 49 M201.75 49 C157.52 49, 113.28 49, 12.25 49 M201.75 49 C159.39 49, 117.04 49, 12.25 49 M12.25 49 C4.08 49, 0 44.92, 0 36.75 M12.25 49 C4.08 49, 0 44.92, 0 36.75 M0 36.75 C0 29.56, 0 22.38, 0 12.25 M0 36.75 C0 27.34, 0 17.92, 0 12.25 M0 12.25 C0 4.08, 4.08 0, 12.25 0 M0 12.25 C0 4.08, 4.08 0, 12.25 0" stroke="#364fc7" stroke-width="1" fill="none"></path></g><g transform="translate(858.4498913143352 148.54983498384172) rotate(0 87.47196197509766 17.5)"><text x="87.47196197509766" y="0" font-family="Virgil, Segoe UI Emoji" font-size="28px" fill="#364fc7" text-anchor="middle" style="white-space: pre;" direction="ltr" dominant-baseline="text-before-edge">12-hour clock</text></g><g stroke-linecap="round" transform="translate(252.28034194509019 143.77126876176044) rotate(0 151.5 22.5)"><path d="M11.25 0 M11.25 0 C96.78 0, 182.31 0, 291.75 0 M11.25 0 C116.84 0, 222.44 0, 291.75 0 M291.75 0 C299.25 0, 303 3.75, 303 11.25 M291.75 0 C299.25 0, 303 3.75, 303 11.25 M303 11.25 C303 19.98, 303 28.7, 303 33.75 M303 11.25 C303 16.06, 303 20.86, 303 33.75 M303 33.75 C303 41.25, 299.25 45, 291.75 45 M303 33.75 C303 41.25, 299.25 45, 291.75 45 M291.75 45 C199.35 45, 106.94 45, 11.25 45 M291.75 45 C209.26 45, 126.77 45, 11.25 45 M11.25 45 C3.75 45, 0 41.25, 0 33.75 M11.25 45 C3.75 45, 0 41.25, 0 33.75 M0 33.75 C0 28.6, 0 23.46, 0 11.25 M0 33.75 C0 27.37, 0 20.99, 0 11.25 M0 11.25 C0 3.75, 3.75 0, 11.25 0 M0 11.25 C0 3.75, 3.75 0, 11.25 0" stroke="#364fc7" stroke-width="1" fill="none"></path></g><g transform="translate(265.69840224782456 148.77126876176044) rotate(0 138.08193969726562 17.5)"><text x="138.08193969726562" y="0" font-family="Virgil, Segoe UI Emoji" font-size="28px" fill="#364fc7" text-anchor="middle" style="white-space: pre;" direction="ltr" dominant-baseline="text-before-edge">day + ordinal suffix</text></g><g stroke-linecap="round"><g transform="translate(424.5794267836254 69.92385997427391) rotate(0 -125.6731232967054 30.834563202678964)"><path d="M0 0 C-41.89 10.28, -209.46 51.39, -251.35 61.67 M0 0 C-41.89 10.28, -209.46 51.39, -251.35 61.67" stroke="#364fc7" stroke-width="1" fill="none"></path></g><g transform="translate(424.5794267836254 69.92385997427391) rotate(0 -125.6731232967054 30.834563202678964)"><path d="M-226.41 44.99 C-233.94 50.02, -241.46 55.05, -251.35 61.67 M-226.41 44.99 C-235.13 50.82, -243.84 56.65, -251.35 61.67" stroke="#364fc7" stroke-width="1" fill="none"></path></g><g transform="translate(424.5794267836254 69.92385997427391) rotate(0 -125.6731232967054 30.834563202678964)"><path d="M-221.52 64.92 C-230.52 63.94, -239.52 62.96, -251.35 61.67 M-221.52 64.92 C-231.95 63.78, -242.37 62.65, -251.35 61.67" stroke="#364fc7" stroke-width="1" fill="none"></path></g></g><mask></mask><g stroke-linecap="round"><g transform="translate(474.3235610494803 67.36992297171128) rotate(0 -47.503355466294124 33.69689152487172)"><path d="M0 0 C-15.83 11.23, -79.17 56.16, -95.01 67.39 M0 0 C-15.83 11.23, -79.17 56.16, -95.01 67.39" stroke="#364fc7" stroke-width="1" fill="none"></path></g><g transform="translate(474.3235610494803 67.36992297171128) rotate(0 -47.503355466294124 33.69689152487172)"><path d="M-77.95 42.71 C-82.8 49.72, -87.64 56.74, -95.01 67.39 M-77.95 42.71 C-82.72 49.61, -87.48 56.51, -95.01 67.39" stroke="#364fc7" stroke-width="1" fill="none"></path></g><g transform="translate(474.3235610494803 67.36992297171128) rotate(0 -47.503355466294124 33.69689152487172)"><path d="M-66.08 59.45 C-74.29 61.71, -82.51 63.96, -95.01 67.39 M-66.08 59.45 C-74.16 61.67, -82.25 63.89, -95.01 67.39" stroke="#364fc7" stroke-width="1" fill="none"></path></g></g><mask></mask><g stroke-linecap="round"><g transform="translate(530.5558386621024 69.0786393204744) rotate(0 57.59662464037228 32.59353591464105)"><path d="M0 0 C19.2 10.86, 95.99 54.32, 115.19 65.19 M0 0 C19.2 10.86, 95.99 54.32, 115.19 65.19" stroke="#364fc7" stroke-width="1" fill="none"></path></g><g transform="translate(530.5558386621024 69.0786393204744) rotate(0 57.59662464037228 32.59353591464105)"><path d="M85.61 60.23 C94.39 61.7, 103.18 63.18, 115.19 65.19 M85.61 60.23 C94.52 61.73, 103.44 63.22, 115.19 65.19" stroke="#364fc7" stroke-width="1" fill="none"></path></g><g transform="translate(530.5558386621024 69.0786393204744) rotate(0 57.59662464037228 32.59353591464105)"><path d="M95.71 42.37 C101.5 49.15, 107.28 55.92, 115.19 65.19 M95.71 42.37 C101.58 49.25, 107.46 56.13, 115.19 65.19" stroke="#364fc7" stroke-width="1" fill="none"></path></g></g><mask></mask><g stroke-linecap="round"><g transform="translate(608.4158429652225 63.01384955924732) rotate(0 124.1112535415059 35.17362352646478)"><path d="M0 0 C41.37 11.72, 206.85 58.62, 248.22 70.35 M0 0 C41.37 11.72, 206.85 58.62, 248.22 70.35" stroke="#364fc7" stroke-width="1" fill="none"></path></g><g transform="translate(608.4158429652225 63.01384955924732) rotate(0 124.1112535415059 35.17362352646478)"><path d="M218.3 72.53 C226.34 71.95, 234.38 71.36, 248.22 70.35 M218.3 72.53 C224.95 72.05, 231.59 71.56, 248.22 70.35" stroke="#364fc7" stroke-width="1" fill="none"></path></g><g transform="translate(608.4158429652225 63.01384955924732) rotate(0 124.1112535415059 35.17362352646478)"><path d="M223.9 52.79 C230.43 57.51, 236.97 62.22, 248.22 70.35 M223.9 52.79 C229.3 56.69, 234.7 60.59, 248.22 70.35" stroke="#364fc7" stroke-width="1" fill="none"></path></g></g><mask></mask></svg>
</div>

</v-click>
