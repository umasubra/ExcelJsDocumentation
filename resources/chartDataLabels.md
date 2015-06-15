# Chart Data Labels
Represents a colection of all the data labels on a chart point or trendline.

## [Properties](#set-chart-datalabels)

| Property         | Type    |Description|Notes |
|:-----------------|:--------|:----------|:-----|
|`position`          |String|Returns or sets the position of the data label. Possible values are: "Invalid", "None", "Center", "InsideEnd", "InsideBase", "OutsideEnd","Left", "Right", "Top","Bottom", "BestFit", "Callout". |DataLabel.Position|
|`separator`         |String|Returns or sets the separator used for the data labels on a chart. |DataLabel.separator|
|`showBubbleSize`          |Boolean|Returns or sets a boolean. True to show the bubble size for the data labels on a chart. False to hide.|DataLabel.showBubbleSize|
|`showCategoryName`          |Boolean|Returns or sets a boolean. True to display the category name for the data labels on a chart. False to hide. |DataLabel.showCategoryName|
|`showLegendKey`          |Boolean| Returns or sets a boolean. True if the data label legend key is visible.  |DataLabel.showLegendKey|
|`showPercentage`          |Boolean|Returns or sets a boolean. True to display the percentage value for the data labels on a chart. False to hide.  |DataLabel.showPercentage|
|`showSeriesName`          |Boolean| Returns or sets a boolean. True to display the series name for the data labels on a chart. False to hide. |DataLabel.showSeriesName|
|`ShowValue`          |Boolean| Returns or sets a boolean. True to display the value for the data labels on a chart. False to hide.|DataLabel.ShowValue|


## Relationships
The ChartDataLabels has the following relationships defined:

| Relationships    | Type    |Description|Notes |
|:-----------------|:--------|:----------|:-----|
| `format`          |[Chart Data Label Format](chartDataLabelFormat.md) Object | Represents the format of chart datalabels, which includes fill(interior/background) and font formatting.

## Methods
None.

## API Specification 


### Set Chart DataLabels

Set the properties of the chart datalables.

#### Syntax

```js
chartObject.datalabels.visible = true;
chartObject.datalabels.position = "top";
chartObject.datalabels.ShowSeriesName = true;
```

#### Properties
| Property         | Type    |Description|Notes |
|:-----------------|:--------|:----------|:-----|
|`position`          |String|Returns or sets the position of the data label. Possible values are: "Invalid", "None", "Center", "InsideEnd", "InsideBase", "OutsideEnd","Left", "Right", "Top","Bottom", "BestFit", "Callout". |DataLabel.Position|
|`separator`         |String|Returns or sets the separator used for the data labels on a chart. |DataLabel.separator|
|`showBubbleSize`          |Boolean|Returns or sets a boolean. True to show the bubble size for the data labels on a chart. False to hide.|DataLabel.showBubbleSize|
|`showCategoryName`          |Boolean|Returns or sets a boolean. True to display the category name for the data labels on a chart. False to hide. |DataLabel.showCategoryName|
|`showLegendKey`          |Boolean| Returns or sets a boolean. True if the data label legend key is visible.  |DataLabel.showLegendKey|
|`showPercentage`          |Boolean|Returns or sets a boolean. True to display the percentage value for the data labels on a chart. False to hide.  |DataLabel.showPercentage|
|`showSeriesName`          |Boolean| Returns or sets a boolean. True to display the series name for the data labels on a chart. False to hide. |DataLabel.showSeriesName|
|`ShowValue`          |Boolean| Returns or sets a boolean. True to display the value for the data labels on a chart. False to hide.|DataLabel.ShowValue|


#### Returns
None.


#### Examples
##### Make Series Name shown in Datalabels and set the `position` of datalabels to be "top";
```js
var ctx = new Excel.ExcelClientContext();
var chart = ctx.workbook.worksheets.getItem("Sheet1").charts.getItem("Chart1");	

chart.datalabels.visible = true;
chart.datalabels.position = "top";
chart.datalabels.ShowSeriesName = true;

ctx.executeAsync().then(function () {
		logComment("Datalabels Shown");
});
```
[Back](#properties)