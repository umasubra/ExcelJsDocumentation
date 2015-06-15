# Chart Title
Represents the title of a chart. 

## [Properties](#get-chart-title)

| Property         | Type    |Description|Notes |
|:-----------------|:--------|:----------|:-----|
| `text` | String |Returns or sets the title of a chart. When a title is set, the display property will be automatically set to Top and the chart title will be displayed on the top of the chart without overlapping. | Chart.ChartTitle |
| `visible` | Boolean |Returns or seta a boolean that represents the visibility of a chart title object. If set to true, the chart title will be visible on the chart. |  |
| `overlay` | Boolean |Returns or sets a boolean. True if the title overlays the chart. | Chart.ChartTitle.Position |

## Relationships
The ChartTitle object has the following relationships defined:

| Relationships    | Type    |Description|Notes |
|:-----------------|:--------|:----------|:-----|
| `format`          |[ChartTitleFormat](chartTitleFormat.md) object | Represents the formatting of a chart title, which includes fill(interior/background) and font formatting.
     
## Methods
None.

## API Specification 

### Get Chart Title

Gets the title of a chart.

#### Syntax
```js
chartObject.title;
```
#### Properties
| Property         | Type    |Description|Notes |
|:-----------------|:--------|:----------|:-----|
| `text` | String |Returns or sets the title of a chart. When a title is set, the display property will be automatically set to Top and the chart title will be displayed on the top of the chart without overlapping. | Chart.ChartTitle |
| `visible` | Boolean |Returns or seta a boolean that represents the visibility of a chart title object. If set to true, the chart title will be visible on the chart. |  |
| `overlay` | Boolean |Returns or sets a boolean. True if the title overlays the chart. | Chart.ChartTitle.Position |

#### Returns

[ChartTitle](chartTitle.md) object. 

#### Examples

##### Get the `text` of Chart Title from Chart1
```js
var ctx = new Excel.ExcelClientContext();
var chart = ctx.workbook.worksheets.getItem("Sheet1").charts.getItem("Chart1");	

var title = chart.title;
ctx.load(title);
ctx.executeAsync().then(function () {
		logComment(title.text);
});
```

[Back](#properties)

### Set Chart Title

Sets the properties of a chart title, including text and visibility.

#### Syntax

```js
chartObject.title.text= "My Chart"; 
chartObject.title.visible=true;
chartObject.title.overlay=true;
```

#### Properties
| Property         | Type    |Description|Notes |
|:-----------------|:--------|:----------|:-----|
| `text` | String |Returns or sets the title of a chart. When a title is set, the display property will be automatically set to Top and the chart title will be displayed on the top of the chart without overlapping. | Chart.ChartTitle |
| `visible` | Boolean |Returns or seta a boolean that represents the visibility of a chart title object. If set to true, the chart title will be visible on the chart. |  |
| `overlay` | Boolean |Returns or sets a boolean. True if the title overlays the chart. | Chart.ChartTitle.Position |

#### Returns

[ChartTitle](chartTitle.md) object. 


#### Examples

##### Set the `text` of Chart Title to "My Chart" and Make it show on top of the chart without overlaying.
```js
var ctx = new Excel.ExcelClientContext();
var chart = ctx.workbook.worksheets.getItem("Sheet1").charts.getItem("Chart1");	

chart.title.text= "My Chart"; 
chart.title.visible=true;
chart.title.overlay=true;

ctx.executeAsync().then(function () {
		logComment("Char Title Changed");
});
```
[Back](#properties)