# Chart Configuration

Chart.js provides a wide range of configuration options to customize your charts. This guide covers the major configuration options, including scales, plugins, and dataset options.

## Table of Contents

1. [Basic Configuration](#basic-configuration)
2. [Chart Options](#chart-options)
3. [Scale Configuration](#scale-configuration)
4. [Plugin Configuration](#plugin-configuration)
5. [Dataset Configuration](#dataset-configuration)
6. [Common Customizations](#common-customizations)

## Basic Configuration

To create a chart, you need to provide a configuration object that defines the chart type, data, and options. Here's a basic example:

```javascript
const config = {
  type: 'bar',
  data: {
    labels: ['January', 'February', 'March', 'April', 'May', 'June', 'July'],
    datasets: [{
      label: 'My First Dataset',
      data: [65, 59, 80, 81, 56, 55, 40],
      backgroundColor: 'rgba(75, 192, 192, 0.2)',
      borderColor: 'rgba(75, 192, 192, 1)',
      borderWidth: 1
    }]
  },
  options: {
    responsive: true,
    scales: {
      y: {
        beginAtZero: true
      }
    }
  }
};

const myChart = new Chart(ctx, config);
```

## Chart Options

Chart options are used to customize the overall appearance and behavior of the chart. Some common options include:

- `responsive`: Boolean, default `true`. Resizes the chart canvas when its container does.
- `aspectRatio`: Number, default `2`. Canvas aspect ratio (i.e. width / height) for resize.
- `maintainAspectRatio`: Boolean, default `true`. Maintain the original canvas aspect ratio when resizing.
- `plugins`: Object. Plugin specific options.

Example:

```javascript
const config = {
  type: 'line',
  data: data,
  options: {
    responsive: true,
    aspectRatio: 1.5,
    plugins: {
      title: {
        display: true,
        text: 'Custom Chart Title'
      }
    }
  }
};
```

## Scale Configuration

Scales are used to display axes in the chart. Chart.js supports various scale types, including linear, logarithmic, and time scales.

Example of configuring scales:

```javascript
const config = {
  type: 'line',
  data: data,
  options: {
    scales: {
      x: {
        type: 'time',
        time: {
          unit: 'month'
        }
      },
      y: {
        type: 'linear',
        beginAtZero: true,
        title: {
          display: true,
          text: 'Value'
        }
      }
    }
  }
};
```

## Plugin Configuration

Plugins can be used to extend the functionality of Chart.js. Some built-in plugins include Legend, Title, and Tooltip.

Example of configuring plugins:

```javascript
const config = {
  type: 'bar',
  data: data,
  options: {
    plugins: {
      legend: {
        position: 'top',
      },
      title: {
        display: true,
        text: 'Chart Title'
      },
      tooltip: {
        mode: 'index',
        intersect: false,
      }
    }
  }
};
```

## Dataset Configuration

Dataset options allow you to customize the appearance and behavior of individual datasets in the chart.

Example of dataset configuration:

```javascript
const config = {
  type: 'line',
  data: {
    labels: ['January', 'February', 'March', 'April', 'May', 'June', 'July'],
    datasets: [{
      label: 'Dataset 1',
      data: [65, 59, 80, 81, 56, 55, 40],
      fill: false,
      borderColor: 'rgb(75, 192, 192)',
      tension: 0.1
    }, {
      label: 'Dataset 2',
      data: [28, 48, 40, 19, 86, 27, 90],
      fill: false,
      borderColor: 'rgb(255, 99, 132)',
      tension: 0.1
    }]
  },
  options: {
    responsive: true,
    plugins: {
      title: {
        display: true,
        text: 'Chart.js Line Chart'
      },
    },
    interaction: {
      mode: 'index',
      intersect: false
    },
    scales: {
      x: {
        display: true,
        title: {
          display: true,
          text: 'Month'
        }
      },
      y: {
        display: true,
        title: {
          display: true,
          text: 'Value'
        }
      }
    }
  },
};
```

## Common Customizations

Here are some common customizations you might want to apply to your charts:

1. Changing colors:

```javascript
const config = {
  type: 'bar',
  data: {
    datasets: [{
      backgroundColor: ['rgba(255, 99, 132, 0.2)', 'rgba(54, 162, 235, 0.2)'],
      borderColor: ['rgba(255, 99, 132, 1)', 'rgba(54, 162, 235, 1)'],
    }]
  }
};
```

2. Customizing tooltips:

```javascript
const config = {
  type: 'line',
  data: data,
  options: {
    plugins: {
      tooltip: {
        callbacks: {
          label: function(context) {
            return `${context.dataset.label}: $${context.parsed.y}`;
          }
        }
      }
    }
  }
};
```

3. Adding a second y-axis:

```javascript
const config = {
  type: 'line',
  data: {
    datasets: [{
      yAxisID: 'y',
    }, {
      yAxisID: 'y1',
    }]
  },
  options: {
    scales: {
      y: {
        type: 'linear',
        display: true,
        position: 'left',
      },
      y1: {
        type: 'linear',
        display: true,
        position: 'right',
        grid: {
          drawOnChartArea: false,
        },
      }
    }
  }
};
```

Remember that Chart.js is highly customizable, and these examples only scratch the surface of what's possible. For more detailed information on specific configuration options, refer to the Chart.js documentation for each chart type and component.