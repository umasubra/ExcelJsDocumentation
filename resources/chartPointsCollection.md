# Chart Point Collection
A collection of all the ChartPoint objects in a chart. 

## [Properties](#get-chartpoint-collection)

| Property         | Type    |Description|Notes |
|:-----------------|:--------|:----------|:-----|
|`count`| Number   | Returns the number of chart points in the collection.||
|`items`| [Chart Point](chartPoint.md) array | Returns a collection of all the chart points  in a chart.| |

## Relationships

None

## Methods

The chartPointsColleciton object has the following methods defined:

| Method     | Return Type    |Description|Notes  |
|:-----------------|:--------|:----------|:------|
|[getItemAt(index: number)](#getitematindex-number)| [ChartPoint](chartPoint.md)     |Gets a ChartPoint object based on its position in the items[] array.||


## API Specification 

### Get ChartPoint Collection

Gets a collection of all the ChartPoint objects in a chart.

#### Syntax
```js
chartObject.points;	
```

#### Properties

| Property         | Type    |Description|Notes |
|:-----------------|:--------|:----------|:-----|
|`count`| Number   | Returns the number of chart points in the collection.||
|`items`| [Chart Point](chartPoint.md) array | Returns a collection of all the chart points in a chart.| ||

#### Returns

[ChartPoint](chartPoint.md) collection. 

#### Examples

##### Getting the names of points in the points collection
```js
var ctx = new Excel.ExcelClientContext();
var pointsCollection = ctx.workbook.worksheets.getItem("Sheet1").charts.getItem("Chart1").points;
ctx.load(pointsCollection);
ctx.executeAsync().then(function () {
	Console.log("Points Collection loaded");
});
```

##### Getting the number of points

```js
var ctx = new Excel.ExcelClientContext();
var pointsCollection = ctx.workbook.worksheets.getItem("Sheet1").charts.getItem("Chart1").points;
ctx.load(pointsCollection);
ctx.executeAsync().then(function () {
	Console.log("points: Count= " + pointsCollection.count);
});

```
[Back](#properties)


### getItemAt(index: number)

Gets a ChartPoint object based on its position in the items[] array. 

#### Syntax
```js
ChartPointsCollection.getItemAt(index);
```

#### Parameters

Parameter       | Type  | Description
--------------- | ------ | ------------
 `index`| Number | Required. Index or position in the items[] array. Zero-indexed.

#### Returns

[ChartPoint](chartPoint.md) object.

#### Examples

##### Set the border color for the first points in the points collection
```js
var ctx = new Excel.ExcelClientContext();
var point = ctx.workbook.worksheets.getItem("Sheet1").charts.getItem("Chart1").series.getItemAt(0).points;
points.getItemAt(0).format.fill.setSolidColor("8FBC8F");
ctx.executeAsync().then(function () {
	Console.log("Point Border Color Changed");
});
```
[Back](#methods)
