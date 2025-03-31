---
title: Chart Types Overview
---

# Chart Types Overview

Chart.js provides a variety of chart types to visualize your data effectively. This page offers an overview of all available chart types, including a brief description, key features, and a basic example for each.

## Bar Chart

Bar charts are used to show comparisons across categories.

**Key Features:**
- Vertical or horizontal orientation
- Stacked or grouped bars
- Customizable bar colors and styles

**Basic Example:**
```javascript
import { BarController } from 'chart.js';

const ctx = document.getElementById('myChart').getContext('2d');
new Chart(ctx, {
    type: 'bar',
    data: {
        labels: ['Red', 'Blue', 'Yellow', 'Green', 'Purple', 'Orange'],
        datasets: [{
            label: '# of Votes',
            data: [12, 19, 3, 5, 2, 3]
        }]
    }
});
```

## Bubble Chart

Bubble charts show data points as circles, with the circle's size representing a third data dimension.

**Key Features:**
- Three-dimensional data visualization
- Customizable bubble colors and sizes

**Basic Example:**
```javascript
import { BubbleController } from 'chart.js';

const ctx = document.getElementById('myChart').getContext('2d');
new Chart(ctx, {
    type: 'bubble',
    data: {
        datasets: [{
            label: 'Bubble Dataset',
            data: [
                { x: 20, y: 30, r: 15 },
                { x: 40, y: 10, r: 10 },
                { x: 15, y: 37, r: 20 }
            ]
        }]
    }
});
```

## Doughnut and Pie Charts

Doughnut and pie charts are circular graphs divided into segments, ideal for showing proportional data.

**Key Features:**
- Customizable segment colors
- Interactive legend
- Optional center hole (for doughnut charts)

**Basic Example (Doughnut):**
```javascript
import { DoughnutController } from 'chart.js';

const ctx = document.getElementById('myChart').getContext('2d');
new Chart(ctx, {
    type: 'doughnut',
    data: {
        labels: ['Red', 'Blue', 'Yellow'],
        datasets: [{
            data: [300, 50, 100]
        }]
    }
});
```

**Basic Example (Pie):**
```javascript
import { PieController } from 'chart.js';

const ctx = document.getElementById('myChart').getContext('2d');
new Chart(ctx, {
    type: 'pie',
    data: {
        labels: ['Red', 'Blue', 'Yellow'],
        datasets: [{
            data: [300, 50, 100]
        }]
    }
});
```

## Line Chart

Line charts display data points connected by straight line segments, useful for showing trends over time.

**Key Features:**
- Multiple datasets
- Customizable line styles (color, width, dash pattern)
- Area fill option

**Basic Example:**
```javascript
import { LineController } from 'chart.js';

const ctx = document.getElementById('myChart').getContext('2d');
new Chart(ctx, {
    type: 'line',
    data: {
        labels: ['January', 'February', 'March', 'April', 'May', 'June', 'July'],
        datasets: [{
            label: 'My First Dataset',
            data: [65, 59, 80, 81, 56, 55, 40]
        }]
    }
});
```

## Polar Area Chart

Polar area charts are similar to pie charts but use the length of the arc to show data values instead of the size of the slice.

**Key Features:**
- Radial chart with adjustable segment sizes
- Useful for comparing multiple variables

**Basic Example:**
```javascript
import { PolarAreaController } from 'chart.js';

const ctx = document.getElementById('myChart').getContext('2d');
new Chart(ctx, {
    type: 'polarArea',
    data: {
        labels: ['Red', 'Green', 'Yellow', 'Grey', 'Blue'],
        datasets: [{
            data: [11, 16, 7, 3, 14]
        }]
    }
});
```

## Radar Chart

Radar charts display multivariate data on a two-dimensional chart with three or more quantitative variables.

**Key Features:**
- Visualize multiple data points and the relationships between them
- Customizable axis and grid lines

**Basic Example:**
```javascript
import { RadarController } from 'chart.js';

const ctx = document.getElementById('myChart').getContext('2d');
new Chart(ctx, {
    type: 'radar',
    data: {
        labels: ['Eating', 'Drinking', 'Sleeping', 'Designing', 'Coding', 'Cycling', 'Running'],
        datasets: [{
            label: 'My First Dataset',
            data: [65, 59, 90, 81, 56, 55, 40]
        }]
    }
});
```

## Scatter Chart

Scatter charts use dots to represent values for two different numeric variables.

**Key Features:**
- Visualize relationships between variables
- Customizable point styles and colors

**Basic Example:**
```javascript
import { ScatterController } from 'chart.js';

const ctx = document.getElementById('myChart').getContext('2d');
new Chart(ctx, {
    type: 'scatter',
    data: {
        datasets: [{
            label: 'Scatter Dataset',
            data: [
                { x: -10, y: 0 },
                { x: 0, y: 10 },
                { x: 10, y: 5 },
                { x: 0.5, y: 5.5 }
            ]
        }]
    }
});
```

Each chart type in Chart.js offers extensive customization options and can be combined to create mixed chart types. For more detailed information on each chart type and its configuration options, please refer to the specific chart type documentation.