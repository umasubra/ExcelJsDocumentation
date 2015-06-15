# Chart Legend
Represents the legend in a chart. Each chart can have only one legend.

## [Properties](#get-chart-legend)

| Property         | Type    |Description|Notes |
|:-----------------|:--------|:----------|:-----|
| `visible` | Boolean |Returns or sets a boolean value the represents the visibility of a ChartLegend object. If visible is set to be ture, the legend will be visible on the chart. |  |
| `position` | String |Returns or sets a legend position value that represents the position of the legend on the chart. Possible values are: `Top`,`Bottom`,`Cornor`,`Left`,`Right`,'Custom', and'Invalid'| Legend.position |
| `overlay` | Boolean |Returns or sets a boolean. True if the legend with be overlapping with the chart. | Legend.IncludeInLayout |


## Relationships
The Chart Legend object has the following relationships defined:

| Relationships    | Type    |Description|Notes |
|:-----------------|:--------|:----------|:-----|
| `format`          |[ChartLegendFormat](chartLegendFormat.md) Object | Represents the format of a chart legend, which includes fill(interior/background) and font formatting.
     

## Methods
None.

## API Specification 
### Get Chart Legend

Gets the legend in a chart.

#### Syntax
```js
chartObject.legend;
```
#### Properties
| Property         | Type    |Description|Notes |
|:-----------------|:--------|:----------|:-----|
| `visible` | Boolean |Returns or sets a boolean value the represents the visibility of a ChartLegend object. If visible is set to be ture, the legend will be visible on the chart. |  |
| `position` | String |Returns or sets a legend position value that represents the position of the legend on the chart. Possible values are: `Top`,`Bottom`,`Cornor`,`Left`,`Right`,'Custom', and'Invalid'| Legend.position |
| `overlay` | Boolean |Returns or sets a boolean. True if the legend with be overlapping with the chart. | Legend.IncludeInLayout | 

#### Returns

[ChartLegend](chartLegend.md) object. 

#### Examples

##### Get the `position` of Chart Legend from Chart1
```js
var ctx = new Excel.ExcelClientContext();
var chart = ctx.workbook.worksheets.getItem("Sheet1").charts.getItem("Chart1");	

var legend = chart.legend;
ctx.load(legend);
ctx.executeAsync().then(function () {
		logComment(legend.position);
});
```

[Back](#properties)

### Set Chart Legend

Set the properties of the legend.

#### Syntax

```js
chartObject.legend.visible = true;
chartObject.legend.position = "top"; 
chartObject.legend.overlay = true;
```

#### Properties
| Property         | Type    |Description|Notes |
|:-----------------|:--------|:----------|:-----|
| `visible` | Boolean |Returns or sets a boolean value the represents the visibility of a ChartLegend object. If visible is set to be ture, the legend will be visible on the chart. |  |
| `position` | String |Returns or sets a legend position value that represents the position of the legend on the chart. Possible values are: `Top`,`Bottom`,`Cornor`,`Left`,`Right`,'Custom', and'Invalid'| Legend.position |
| `overlay` | Boolean |Returns or sets a boolean. True if the legend with be overlapping with the chart. | Legend.IncludeInLayout |

#### Returns
[ChartLegend](chartLegend.md) object. 


#### Examples

##### Show Legend of Chart1 and make it on top of the chart.
```js
var ctx = new Excel.ExcelClientContext();
var chart = ctx.workbook.worksheets.getItem("Sheet1").charts.getItem("Chart1");	

chart.legend.visible = true;
chart.legend.position = "top"; 
chart.legend.overlay = false; 
ctx.executeAsync().then(function () {
		logComment("Legend Shown ");
});
``` 
[Back](#properties)