# 🎨📈 funky-graphs
A JavaScript library for creating advanced, interactive 3D data visualizations in the browser. Built with various JavaScript libraries for stunning visual effects.

## Installation and Setting Up Your Environment
Install via npm (write this in the terminal):
npm install funky-graphs
Set up an HTML file and create a div to host your graph:
```html
<!DOCTYPE html>
<html>
<head>
    <title>My Data Visualization</title>
    <style>
        #plotContainer {
            width: 800px;
            height: 600px;
            border: 1px solid #eee;
            margin: 20px auto;
        }
    </style>
</head>
<body>
    <h1>Revenue Over Time</h1>
    <div id="plotContainer"></div>
    <script type="module" src="./app.js"></script>
</body>
</html>
```
Create a javascript file and import the graph(s) of your choice:
```javascript
import { createWaterfallPlot } from 'funky-graphs';
Call the function and pass the relevant data and parameters in!
createWaterfallPlot('./data.csv', 'chart-container', 'light', 'Time', 'Revenue');
```
