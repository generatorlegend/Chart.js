# Plugin Usage Guide

Chart.js provides a powerful plugin system that allows you to extend and customize chart functionality. This guide will help you understand how to use built-in plugins, configure them, and provide examples of common plugin usage scenarios.

## Table of Contents

1. [Introduction to Chart.js Plugins](#introduction-to-chartjs-plugins)
2. [Built-in Plugins](#built-in-plugins)
3. [Using Plugins](#using-plugins)
4. [Configuring Plugins](#configuring-plugins)
5. [Common Plugin Usage Examples](#common-plugin-usage-examples)

## Introduction to Chart.js Plugins

Plugins are a way to extend Chart.js functionality, allowing you to add new features or modify existing behavior. They can be used to add new chart elements, modify data processing, or interact with the rendering process.

## Built-in Plugins

Chart.js comes with several built-in plugins that you can use out of the box. These plugins are:

- Colors
- Decimation
- Filler
- Legend
- SubTitle
- Title
- Tooltip

You can find these plugins in the `src/plugins/index.js` file of the Chart.js source code.

## Using Plugins

To use a plugin in your Chart.js project, you need to import and register it. For built-in plugins, this is typically done automatically when you import Chart.js. However, you can also manually register plugins if needed.

Here's an example of how to import and use a built-in plugin:

```javascript
import Chart from 'chart.js/auto';
import { Legend } from 'chart.js';

// Register the plugin (not necessary for built-in plugins, but shown for demonstration)
Chart.register(Legend);

// Create a chart with the plugin
const chart = new Chart(ctx, {
    type: 'bar',
    data: { /* ... */ },
    options: {
        plugins: {
            legend: {
                position: 'top',
            }
        }
    }
});
```

## Configuring Plugins

Most plugins can be configured through the `options.plugins` object in your chart configuration. Each plugin typically has its own set of options that you can customize.

Here's an example of configuring multiple plugins:

```javascript
const chart = new Chart(ctx, {
    type: 'line',
    data: { /* ... */ },
    options: {
        plugins: {
            legend: {
                display: true,
                position: 'bottom'
            },
            title: {
                display: true,
                text: 'My Chart Title'
            },
            tooltip: {
                enabled: true,
                mode: 'index'
            }
        }
    }
});
```

## Common Plugin Usage Examples

### 1. Customizing the Legend

```javascript
const chart = new Chart(ctx, {
    type: 'pie',
    data: { /* ... */ },
    options: {
        plugins: {
            legend: {
                position: 'right',
                labels: {
                    font: {
                        size: 14
                    },
                    color: 'rgb(255, 99, 132)'
                }
            }
        }
    }
});
```

### 2. Adding a Title and Subtitle

```javascript
const chart = new Chart(ctx, {
    type: 'bar',
    data: { /* ... */ },
    options: {
        plugins: {
            title: {
                display: true,
                text: 'Sales Report',
                font: {
                    size: 20
                }
            },
            subtitle: {
                display: true,
                text: 'Monthly breakdown of product sales',
                padding: {
                    top: 10,
                    bottom: 30
                }
            }
        }
    }
});
```

### 3. Customizing Tooltips

```javascript
const chart = new Chart(ctx, {
    type: 'scatter',
    data: { /* ... */ },
    options: {
        plugins: {
            tooltip: {
                callbacks: {
                    label: function(context) {
                        return `X: ${context.parsed.x}, Y: ${context.parsed.y}`;
                    }
                },
                backgroundColor: 'rgba(0, 0, 0, 0.7)',
                titleFont: {
                    weight: 'bold'
                }
            }
        }
    }
});
```

By using and configuring plugins, you can greatly enhance the functionality and appearance of your Chart.js charts. Experiment with different plugin options to create charts that best suit your needs.