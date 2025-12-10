# Butterfly Chart 
```javascript
createButterflyChart({
  containerSelector,
  statusSelector,
  sortButtonSelector,
  labels,
  dataSource,
  chartTitle,
  initialMode
});
```
<img width="1170" height="695" alt="butterfly-main" src="https://github.com/user-attachments/assets/8b16c4c0-78dd-4088-8027-46d936aba91f" />


---

## Setup

You'll need to have set up a div to host the plot. This plot also expects a status element and a sort button. You can copy and paste this snippet into your HTML file:

```html
<button id="sortBtn">
  Sorted by Diff
</button>

<p id="statusMsg"></p>

<div id="chart"></div>

<div id="tip"></div>
<div id="detailScreen"></div>

<script src="https://cdn.jsdelivr.net/npm/d3@7"></script>
<script type="module" src="./new.js"></script>
```

Note that this visualization expects the ids to match the parameters you pass:

- `containerSelector` should point to `#chart`.
- `statusSelector` should point to `#statusMsg`.
- `sortButtonSelector` should point to `#sortBtn`.

You can change these ids as long as you also update the corresponding parameters in the function call.

---

## Parameters

```javascript
createButterflyChart({
  containerSelector,
  statusSelector,
  sortButtonSelector,
  labels,
  dataSource,
  chartTitle,
  initialMode
});
```

### *containerSelector*
(string) CSS selector for the HTML div that will host the butterfly plot.

Example: `'#chart'`.

---

### *statusSelector*
(string or null) CSS selector for the element where the chart writes status messages, such as
"Showing top 20 of 20 categories alphabetically by category."  

Example: `'#statusMsg'`.

---

### *sortButtonSelector*
(string or null) CSS selector for the HTML button that toggles the sort mode (A–Z vs by difference).  

Example: `'#sortBtn'`.

---

### *labels*
(object) Text labels for the left and right sides of the butterfly chart.

Example:
```javascript
labels = {
  left: 'Exports',
  right: 'Imports'
};
```

- `left`: Label shown above the left side of the chart.
- `right`: Label shown above the right side of the chart.

---

### *dataSource*
(object) Configuration for loading and mapping your data.

```javascript
dataSource = {
  type: 'csv',
  url: 'countries.csv',
  categoryCol: 'country',
  leftCol: 'exports',
  rightCol: 'imports',
  rightScale: 1
};
```

- **type** (string)  
  Data format. For this project, `'csv'`.

- **url** (string)  
  File path or name of the CSV relative to the HTML file.

- **categoryCol** (string)  
  Column name used for category labels (y‑axis). For example, `'country'`.

- **leftCol** (string)  
  Column name for numeric values plotted on the left side (e.g. `'exports'`).

- **rightCol** (string)  
  Column name for numeric values plotted on the right side (e.g. `'imports'`).

- **rightScale** (float or int)  
  Optional scale factor that multiplies the right‑side values after loading. Default is `1`.

A valid CSV for this configuration looks like:

```csv
country,child_mort,exports,health,imports,income,inflation,life_expectation,total_fer,gdpp
Afghanistan,90.2,10,7.58,44.9,1610,9.44,56.2,5.82,553
Albania,16.6,28,6.55,48.6,9930,4.49,76.3,1.65,4090
Algeria,27.3,38.4,4.17,31.4,12900,16.1,76.5,2.89,4460
...
```

Here:

- `categoryCol` → `country`  
- `leftCol` → `exports`  
- `rightCol` → `imports`

---

### *chartTitle*
(string) The title shown at the top of the page and in the header.

Example: `'Exports vs Imports by Country'`.

---

### *initialMode*
(string: `'dark'` or `'light'`)  
Controls the color theme of the chart.

- `'dark'` → dark background, light text.  
- `'light'` → light background, dark text.

If omitted, the default is `'dark'`.

---

## Example Use And Output

```javascript
import { createButterflyChart } from 'funky-graphs';

createButterflyChart({
  containerSelector: '#chart',            // html div id for chart
  statusSelector: '#statusMsg',           // id for status text
  sortButtonSelector: '#sortBtn',         // id for sort button
  labels: { left: 'Exports', right: 'Imports' }, // left and right axis labels
  dataSource: {
    type: 'csv',                          // data file type
    url: 'countries.csv',                 // name of csv file
    categoryCol: 'country',               // category name column
    leftCol: 'exports',                   // left side values
    rightCol: 'imports',                  // right side values
    rightScale: 1                         // scale factor for right side
  },
  chartTitle: 'Exports vs Imports by Country', // chart title text
  initialMode: 'dark'                     // color theme
});
```
<img width="1066" height="409" alt="butterfly-detail" src="https://github.com/user-attachments/assets/1681c930-438f-4f43-9cfb-e8ede6fa6143" />
