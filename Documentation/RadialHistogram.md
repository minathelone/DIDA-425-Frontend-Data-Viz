# Radial Histogram 
```javascript
  createRadicalHistogram(jsonFile,
  svgId,
  theme,
  width,
  height,
  innerRadius,
  categoryKey
  );
```
<img width="646" height="651" alt="Screen Shot 2025-12-09 at 11 46 41 PM" src="https://github.com/user-attachments/assets/c18941c1-5cb2-45a1-852a-59616f17af4f" />

## Setup
```html
<div id="chart-container">
    <svg id="radial-histogram"></svg>
</div>

<div id="controls">
    <button id="sortValue">Sort: Most → Least</button>
    <button id="sortCategory">Sort: Category</button>
    <button id="reset">Reset</button>
</div>
```
## Parameters
### **jsonFile**: 
```
[ {"title":"Inception","genre":"Sci-Fi","minutes_watched":540000,"unique_viewers":230000,"rating":8.8},
  {"title":"Barbie","genre":"Comedy","minutes_watched":720000,"unique_viewers":310000,"rating":7.1},
  {"title":"Oppenheimer","genre":"Drama","minutes_watched":690000,"unique_viewers":280000,"rating":8.6},
  {"title":"Parasite","genre":"Thriller","minutes_watched":410000,"unique_viewers":200000,"rating":8.5},
  {"title":"Get Out","genre":"Horror","minutes_watched":350000,"unique_viewers":150000,"rating":7.7}
]
```
### *svgId*: 
(string) The id of the html div container that you want to host your waterfall plot in.   
### *theme*: 
(string: "dark" or "light"); toggles between a black or white background.  
### *width*: 
(int) The title for your visualization.  
### *height*: 
(nt) To adjust the (x,y,z) positioning of the title in the full 3D view. The parameter increments default (x/y/z) position.
### *innerRadius*: 
(int) To adjust the (x,y,z) positioning of the title in the isolated slice view. The parameter adds to the default (x/y/z) position.
### *categoryKey*: 
(string) The title for your x axis.  

## Example Use and Output
```javascript
import { createRadicalHistogram } from 'funky-graphs';
createRadicalHistogram('/src/data.json',
    "radial-histogram",
    'dark',
    600,
    600,
    150,
    "genre"
    );
```
<img width="1292" height="1302" alt="image" src="https://github.com/user-attachments/assets/db56907a-9d76-4dd2-9f18-11d6078890b7" />

