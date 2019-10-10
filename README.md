<div align="center">
    <img src="logo.bmp"/>
</div>

# TSGauge

Extension for Chart.js that allows you to draw "Speedometer" graphs.

### Compatibility
Requires [Chart.js](https://github.com/chartjs/Chart.js/releases) **2.7.0** or later.

### Install
```html
<script src="Gauge.js"></script>
```

### Example:
```js
var getColor = (value) => `hsl(${(value / 10000) * 120},100%,50%)`;
var ctx = document.getElementById("canvas").getContext("2d");
new Chart(ctx, {
	type: "tsgauge",
	data: {
		datasets: [{
			backgroundColor: [0, 5000, 10000].map(getColor),
			borderWidth: 0,
			gaugeData: {
				value: 7777,
				valueColor: getColor,
			},
			gaugeLimits: [0, 3000, 7000, 10000],
		}],
	},
	options: {
		events: [],
		showMarkers: true,
		labelFormatFn: (number) => new Intl.NumberFormat('en-IN', {
			style: 'currency',
			currency: 'EUR',
			maximumFractionDigits: 0,
			minimumFractionDigits: 0,
		}).format(number),
		markerFormatFn: (number) => new Intl.NumberFormat('en-IN', {
			maximumFractionDigits: 0,
			minimumFractionDigits: 0,
		}).format(number),
		arrowColor: getColor,
	},
});
```
## License

TSGauge is available under the [MIT license](https://opensource.org/licenses/MIT).
