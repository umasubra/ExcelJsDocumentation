# AxisTitle
Represents the title of a specified chart axis.

## [Properties](#get-chart-axis-title)

| Property         | Type    |Description|Notes |
|:-----------------|:--------|:----------|:-----|
| `text` | String |Returns or sets the title of an axis. | 
| `visible` | Boolean |Returns or sets a boolean that specifies the visibility of an axis title. True if the axis or chart has a visible title.  | 

## Relationships
The ChartAxisTitle has the following relationships defined:

| Relationships    | Type    |Description|Notes |
|:-----------------|:--------|:----------|:-----|
| `format`          |[ChartAxisTitleFormat](chartAxisTitleFormat.md) object | Represents the formatting of a chart axis title.

## Methods
None.


## API Specification 

### Get Chart Axis Title

Gets a ChartAxisTitle object.

#### Syntax
Use value axis as an example here.

```js
chartObject.axes.valueaxis.title;
```
| Property         | Type    |Description|Notes |
|:-----------------|:--------|:----------|:-----|
| `text` | String |Returns or sets the title of an axis. | 
| `visible` | Boolean |Returns or sets a boolean that specifies the visibility of an axis title. True if the axis or chart has a visible title.  | 

#### Returns

[ChartAxisTitle](chartAxisTitle.md) object. 

#### Examples

##### Get the `text` of Chart Axis Title from the value axis of Chart1.
```js
var ctx = new Excel.ExcelClientContext();
var chart = ctx.workbook.worksheets.getItem("Sheet1").charts.getItem("Chart1");	

var title = chart.axes.valueaxis.title;
ctx.load(title);
ctx.executeAsync().then(function () {
		logComment(title.text);
});
```

[Back](#properties)

### Set Chart Axis Title

Set the properties of a chart axis title, including text and visibility.

#### Syntax
Use value axis as an example here.
```js
chartObject.axes.valueaxis.title.text= "My Chart"; 
chartObject.axes.valueaxis.title.visible = true;
```

#### Properties
| Property         | Type    |Description|Notes |
|:-----------------|:--------|:----------|:-----|
| `text` | String |Returns or sets the title of an axis. | 
| `visible` | Boolean |Returns or sets a boolean that specifies the visibility of an axis title. True if the axis or chart has a visible title.  |

#### Returns

[ChartAxisTitle](chartAxisTitle.md) object. 


#### Examples

##### Add "Values" as the title for the value Axis
```js
var ctx = new Excel.ExcelClientContext();
var chart = ctx.workbook.worksheets.getItem("Sheet1").charts.getItem("Chart1");	

chart.axes.valueaxis.title.text = "Values";

ctx.executeAsync().then(function () {
		logComment("Axis Title Added ");
});
```
[Back](#properties)