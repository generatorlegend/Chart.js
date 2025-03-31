---
title: Migration Guide
---

# Migration Guide

This guide is designed to help you upgrade from older versions of Chart.js to the current version. We'll highlight major changes, deprecated features, and provide step-by-step instructions for updating your existing charts.

## Upgrading to Chart.js 4.x

Chart.js 4.x introduces several improvements and changes from previous versions. Follow this guide to ensure a smooth transition for your projects.

### Major Changes

1. **Module System**: Chart.js 4.x uses ES6 modules. This change affects how you import and use Chart.js in your projects.

2. **Reduced Bundle Size**: The core library has been optimized, resulting in a smaller bundle size.

3. **Improved TypeScript Support**: Enhanced TypeScript definitions for better type checking and autocompletion.

4. **New Chart Types**: Introduction of new chart types and improvements to existing ones.

### Step-by-Step Migration

1. **Update Installation**

   If you're using npm, update your Chart.js package:

   ```bash
   npm install chart.js@4.x
   ```

2. **Update Import Statements**

   Replace old import statements with the new ES6 module syntax:

   ```javascript
   // Old
   import Chart from 'chart.js';

   // New
   import { Chart } from 'chart.js';
   ```

3. **Register Components**

   Chart.js 4.x requires explicit registration of components. Add the following code to register all built-in components:

   ```javascript
   import { Chart, registerables } from 'chart.js';
   Chart.register(...registerables);
   ```

   Alternatively, you can register individual components:

   ```javascript
   import { Chart } from 'chart.js';
   import { LineController, LineElement, PointElement, LinearScale } from 'chart.js';

   Chart.register(LineController, LineElement, PointElement, LinearScale);
   ```

4. **Update Configuration Options**

   Some configuration options have been renamed or restructured. Review your chart configurations and update accordingly. For example:

   ```javascript
   // Old
   var chart = new Chart(ctx, {
     type: 'line',
     data: {...},
     options: {
       scales: {
         yAxes: [{
           ticks: {
             beginAtZero: true
           }
         }]
       }
     }
   });

   // New
   var chart = new Chart(ctx, {
     type: 'line',
     data: {...},
     options: {
       scales: {
         y: {
           beginAtZero: true
         }
      }
     }
   });
   ```

5. **Review Deprecated Features**

   Check for any deprecated features you might be using and replace them with their new equivalents. Consult the [official documentation](https://www.chartjs.org/docs/latest/) for detailed information on deprecated features and their replacements.

6. **Update Plugin Usage**

   If you're using plugins, ensure they are compatible with Chart.js 4.x. You may need to update or replace some plugins.

7. **Test Thoroughly**

   After making these changes, thoroughly test your charts to ensure they work as expected. Pay special attention to any custom implementations or complex configurations.

## Breaking Changes

Be aware of these breaking changes when migrating:

- The `scales` option now uses direct scale references instead of arrays.
- Some scale options have been moved or renamed.
- The `hover` configuration has been replaced with `onHover` callbacks.
- The chart type `horizontalBar` has been removed. Use `bar` with `indexAxis: 'y'` instead.

## Additional Resources

- [Chart.js 4.x Documentation](https://www.chartjs.org/docs/latest/)
- [GitHub Repository](https://github.com/chartjs/Chart.js)
- [Release Notes](https://github.com/chartjs/Chart.js/releases)

For more detailed information on specific features or chart types, refer to the respective sections in the official documentation.

Remember to check for updates regularly, as Chart.js continues to evolve with new features and improvements.