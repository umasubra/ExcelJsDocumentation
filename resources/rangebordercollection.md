# Range Border Collection 

Represents the collection of border objects that belong to a range. 

## [Properties](#get-border-collection)

| Property         | Type    |Description|Notes |
|:-----------------|:--------|:----------|:-----|
|`count`| Number   | Returns the number of border objects in the collection.|range.borders.count|
|`items`| [Range Border](rangeborder.md) array |  Returns a collection of all the border objects that belong to a range.|ListObjects |

## Relationships

None

## Methods

The border collection has the following methods defined:

| Method     | Return Type    |Description|Notes  |
|:-----------------|:--------|:----------|:------|
|[getItem(name: string)](#getitemname-string)| [border](rangeborder.md) Object      |Gets a RangeBorder object by name.||

## API Specification 

### Get border Collection

Gets the properties of the border collection. 

#### Syntax
```js
rangeObject.borders.property;
```

#### Properties

| Property         | Type    |Description|Notes |
|:-----------------|:--------|:----------|:-----|
|`count`| Number   | Returns the number of border objects in the collection.|range.borders.count|
|`items`| [Range Border](rangeborder.md) array |  Returns a collection of all the border objects that belong to a range.|ListObjects |


#### Returns

[border](rangeborder.md) collection. 

#### Examples

```js
var sheetName = "Sheet1";
var rangeAddress = "A1:F8";
var ctx = new Excel.ExcelClientContext();
var worksheet = ctx.workbook.worksheets.getItem(sheetName);
var range = worksheet.getRange(rangeAddress);
var borders = range.format.borders;
ctx.load(borders);
ctx.executeAsync().then(function () {
	for (var i = 0; i < borders.items.length; i++)
	{
		Console.log(borders.items[i].sideIndex);
	}
});
```

##### Getting the number of borders

```js
var sheetName = "Sheet1";
var rangeAddress = "F:G";
var ctx = new Excel.ExcelClientContext();
var worksheet = ctx.workbook.worksheets.getItem(sheetName);
var range = worksheet.getRange(rangeAddress);
var borders = range.format.borders;
ctx.load(borders);
ctx.executeAsync().then(function () {
	Console.log(borders.count);
});
```
[Back](#properties)

### Set Range Border 

Sets the border to a range and sets the Color, LineStyle, and Weight properties for the new border.

#### Syntax
```js
borderCollection(sideIndex).property = value;
```
Where, property is one of the following Range's border properties that can be set. 

#### Properties

Property       | Type   | Description
--------------- | ------ | ------------
|lineStyle| String | Returns or sets the line style for the border. Possible values are: `Continuous`: Continuous line, `Dash`: Dashed line, `DashDot`: Alternating dashes and dots, `DashDotDot`: Dash followed by two dots, `Dot`: Dotted line, `Double`: Double line, `None`: No line, `SlantDashDot`: Slanted dashes.|Border.LineStyle|
|weight| String | Returns or sets the weight of the border around a range. Possible values are: `Hairline`: Hairline (thinnest border), `Medium`: Medium, `Thick`: Thick (widest border), `Thin`: Thin.|Border.Weight|
|color| String | Returns or sets the color of the border line using HTML color code representation. |Border.Color's representation in HTML color code.|

**sideIndex values:**

`sideIndex` values | Type  | Description
--------------- | ------ | ------------
`DiagonalDown`  |String | Border running from the upper left-hand corner to the lower right of each cell in the range. 
`DiagonalUp`    |String |Border running from the lower left-hand corner to the upper right of each cell in the range.
`EdgeBottom`    |String |Border at the bottom of the range.
`EdgeLeft`      |String |Border at the left-hand edge of the range.
`EdgeRight`     |String |Border at the right-hand edge of the range.
`EdgeTop`       |String |Border at the top of the range.
`InsideHorizontal` |String|Horizontal borders for all cells in the range except borders on the outside of the range.
`InsideVertical`|String |Vertical borders for all the cells in the range except borders on the outside of the range.

#### Example
The example below adds grid border around the range.

```js
var sheetName = "Sheet1";
var rangeAddress = "F:G";
var range = ctx.workbook.worksheets.getItem(sheetName).getRange(rangeAddress);
range.format.borders('InsideHorizontal').lineStyle = 'Continuous';
range.format.borders('InsideVertical').lineStyle = 'Continuous';
range.format.borders('EdgeBottom').lineStyle = 'Continuous';
range.format.borders('EdgeLeft').lineStyle = 'Continuous';
range.format.borders('EdgeRight').lineStyle = 'Continuous';
range.format.borders('EdgeTop').lineStyle = 'Continuous';
ctx.executeAsync().then();
```
[Back](#properties)

### getItem(name: string)

Gets the border object by name.

#### Syntax
```js
borderCollection.getItem(name);
```

#### Parameters

Parameter       | Type  | Description
--------------- | ------ | ------------
 `name`| String | Required. border name. 

#### Returns

[border](rangeborder.md) object.

#### Examples
```js
var ctx = new Excel.ExcelClientContext();
var borderName = 'border1';
var border = ctx.workbook.borders.getItem(borderName);
ctx.executeAsync().then(function () {
		Console.log(border.index);
});
```
[Back](#methods)
