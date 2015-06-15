# Chart
Represents a chart in a workbook.

## [Properties](#get-chart)

| Property         | Type    |Description|Notes |
|:-----------------|:--------|:----------|:-----|
| `name`  | String | Returns or sets the name of the chart.   | Chart.Name      |
| `height`| Number | Returns or sets the height of the chart, in points. | ChartArea.Height|
| `width` | Number | Returns or sets the width of the chart, in points. | ChartArea.Width |
| `top` | Number | Returns or sets the distance, in points, from the top edge of the object to the top of row 1 (on a worksheet) or the top of the chart area (on a chart).| ChartArea.Top |
| `left` | Number | Returns or sets the distance, in points, from the left edge of the object to the left edge of column A (on a worksheet) or the left edge of the chart area (on a chart).| ChartArea.Left |


## Relationships

| Relationships    | Type    |Description|Notes |
|:-----------------|:--------|:----------|:-----|
| `title`          |[ChartTitle](chartTitle.md) object | Returns a ChartTitle object that represents the title of the specified chart, including the text, visibility, position and formating of the title.
| `series`         |[Chart Series Collection](chartSeriesCollection.md) |Returns an object that represents either a single series or collection of series in the chart.
| `axes`          |[Chart Axes](chartAxes.md) object |Returns an object that represents a collection of all the axes in the Chart.
| `dataLabels`          |[Chart Data Labels](chartDataLabels.md) object | Returns an object that represents a collection of all the datalabels on the chart.
| `legend`          |[Chart Legend](chartLegend.md) object | Returns a Legend object that represents the legend for the chart. 
| `format`          |[Chart Area Format](chartareaformat.md) object | Returns an object that represents the format of a chart object, which includes fill(interior/background), line/border and font formatting.

## Methods

| Method     | Return Type    |Description|Notes  |
|:-----------------|:--------|:----------|:------|
|[delete()](#delete)| void     |Deletes the chart. ||
|[setData(sourceData: string, seriesBy: string)](#setdatasourcedata-string-seriesby-string)| [Chart](Chart.md)  object |Sets the source data range for the chart.          

## API Specification 

### delete()

Deletes the chart.

#### Syntax

```js
chartObject.delete();
```

#### Parameters
None.

#### Returns

Nothing.

#### Examples

##### Delete the Chart named "Chart1"

```js
var ctx = new Excel.ExcelClientContext();
var chart = ctx.workbook.worksheets.getItem("Sheet1").charts.getItem("Chart1");	

chart.delete();
ctx.executeAsync().then(function () {
		logComment"Chart Deleted");
});
```
[Back](#methods)


### setData(sourceData: string, seriesBy: string)

Sets the source data range for the chart.

#### Syntax

```js
chartObject.setData(sourceData, seriesBy);
```

#### Parameters
| Parameter         | Value    |Description|
|:-----------------|:--------|:----------|
| `sourceData`  | String|  The address or name of the range that contains the source data.|
| `seriesBy`  | String |  Specifies the way columns or rows are used as data series on the chart. Can be one of the following: `Rows`, `Columns` or `Auto`.|

#### Returns

[Chart](chart.md) object. 

#### Examples

##### Set the `sourceData` to be "A1:B4" and `seriesBy` to be "Columns"
```js
var ctx = new Excel.ExcelClientContext();
var chart = ctx.workbook.worksheets.getItem("Sheet1").charts.getItem("Chart1");	
var sourceData = "A1:B4";

chart.setData(sourceData, "Columns");
ctx.executeAsync().then();
```
[Back](#methods)

### Get Chart

Gets a chart object by name.

#### Syntax
```js
chartsCollection.getItem(name);	
```

#### Parameters
None.

#### Returns

[Chart](chart.md) object. 

#### Examples

##### Get the Chart named "Chart1"
```js
var ctx = new Excel.ExcelClientContext();
var chart = ctx.workbook.worksheets.getItem("Sheet1").charts.getItem("Chart1");	

ctx.load(chart);
ctx.executeAsync().then(function () {
		logComment("Chart1 Loaded");
});
```

[Back](#properties)

### Set Chart

Update a chart including renaming, positioning and resizing.

#### Syntax

```js
chartObject.name="New Name";
chartObject.top = 100;
chartObject.left = 100;
chartObject.height = 200;
chartObject.weight = 200;
```

#### Properties
| Property         | Type    |Description|Notes |
|:-----------------|:--------|:----------|:-----|
| `name`  | String | Returns or sets the name of the chart.   | Chart.Name      |
| `height`| Number | Returns or sets the height of the chart, in points. | ChartArea.Height|
| `width` | Number | Returns or sets the width of the chart, in points. | ChartArea.Width |
| `top` | Number | Returns or sets the distance, in points, from the top edge of the object to the top of row 1 (on a worksheet) or the top of the chart area (on a chart).| ChartArea.Top |
| `left` | Number | Returns or sets the distance, in points, from the left edge of the object to the left edge of column A (on a worksheet) or the left edge of the chart area (on a chart).| ChartArea.Left |

#### Returns

[Chart](chart.md) object. 

#### Examples

##### Rename the chart to new name, resize the chart to 200 points in both height and weight. Move Chart1 to 100 points to the top and left. 
```js
var ctx = new Excel.ExcelClientContext();
var chart = ctx.workbook.worksheets.getItem("Sheet1").charts.getItem("Chart1");

chart.name="New Name";	
chart.top = 100;
chart.left = 100;
chart.height =200;
chart.width =200;
ctx.executeAsync().then(function () {
		logComment("Chart Updated");
});
```
[Back](#properties)
