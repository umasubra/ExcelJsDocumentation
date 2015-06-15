# Chart Series Collection
Represents a collection of all the chartSeries objects in a chart. 

## [Properties](#get-chartseries-collection)

| Property         | Type    |Description|Notes |
|:-----------------|:--------|:----------|:-----|
|`count`| Number   | Returns the number of series in the collection.||
|`items`| [Chart Series](chartSeries.md) array |Returns a collection of all the series in the chart.||

## Relationships

None

## Methods

The chart has the following methods defined:

| Method     | Return Type    |Description|Notes  |
|:-----------------|:--------|:----------|:------|
|[getItemAt(index: number)](#getitematindex-number)| [ChartSeries](chartSeries.md)     |Gets a ChartSeries object based on its position in the items[] array.||


## API Specification 

### Get ChartSeries Collection

Gets a collection of all the chartSeries objects in a chart. 

#### Syntax
```js
chartObject.series;	
```

#### Properties

| Property         | Type    |Description|Notes |
|:-----------------|:--------|:----------|:-----|
|`count`| Number   | Returns the number of series in the collection.||
|`items`| [Chart Series](chartSeries.md) array |Returns a collection of all the series in the chart.||


#### Returns

[ChartSeries](chartSeries.md) collection. 

#### Examples

##### Getting the names of series in the series collection
```js
var ctx = new Excel.ExcelClientContext();
var seriesCollection = ctx.workbook.worksheets.getItem("Sheet1").charts.getItem("Chart1").series;
ctx.load(seriesCollection);
ctx.executeAsync().then(function () {
	for (var i = 0; i < seriesCollection.items.length; i++)
	{
		Console.log(seriesCollection.items[i].name);
	}
});
```

##### Getting the number of series

```js
var ctx = new Excel.ExcelClientContext();
var seriesCollection = ctx.workbook.worksheets.getItem("Sheet1").charts.getItem("Chart1").series;
ctx.load(seriesCollection);
ctx.executeAsync().then(function () {
	Console.log("series: Count= " + seriesCollection.count);
});

```
[Back](#properties)


### getItemAt(index: number)

Gets a ChartSeries object based on its position in the items[] array. 

#### Syntax
```js
ChartSeriesCollection.getItemAt(index);
```

#### Parameters

Parameter       | Type  | Description
--------------- | ------ | ------------
 `index`| Number | Required. Index or position in the items[] array. Zero-indexed.

#### Returns

[chartSeries](chartSeries.md) object.

#### Examples

##### Getting the name of the first series in the series collection
```js
var ctx = new Excel.ExcelClientContext();
var seriesCollection = ctx.workbook.worksheets.getItem("Sheet1").charts.getItem("Chart1").series;
ctx.load(seriesCollection);
ctx.executeAsync().then(function () {
	Console.log(seriesCollection.items[0].name);
});
```
[Back](#methods)
