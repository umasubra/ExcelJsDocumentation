# Worksheet Collection
Represents a collection of all the worksheet objects that are part of the workbook. 

## [Properties](#get-worksheet-collection)

| Property         | Type    |Description|Notes |
|:-----------------|:--------|:----------|:-----|
|`count`| Number   | Returns the number of worksheets in the workbook.|Worksheets.count|
|`items`| [Worksheet](worksheet.md) array | Returns a collection of all the worksheet objects that are part of the workbook.|[Worksheets.item] |

## Relationships

None

## Methods

The Worksheet collection has the following methods defined:

| Method     | Return Type    |Description|Notes  |
|:-----------------|:--------|:----------|:------|
|[add(name: string)](#addname-string)| [Worksheet](worksheet.md) Object              |Adds a new worksheet. The new worksheet becomes the active sheet in the workbook. ||
|[getActiveWorksheet()](#getactiveworksheet)| [Worksheet](worksheet.md) object |Gets the currently active worksheet in the workbook.| |
|[getItem(param: string)](#getitemparam-string)| [Worksheet](worksheet.md) Object      |Gets a worksheet object by name.||
|[getItemAt(index: number)](#getitematindex-number)| [Worksheet](worksheet.md) Object     |Gets a worksheet object based on its position in the items[] array.||


## API Specification 

### add(name: string)

Adds a new worksheet to the workbook. The worksheet will be added at the end of existing worksheets and the new worksheet becomes the active sheet in the workbook.

#### Syntax
```js
worksheetCollection.add(name);
```

#### Parameters

Parameter       | Type   | Description
--------------- | ------ | ------------
`name`  | String| Optional. The name of the sheet to be added. If not specified, Excel determines the name of the new worksheet being added. 

#### Returns
[Worksheet](worksheet.md) object.

#### Examples

```js
var wSheetName = 'Sample Name';
var ctx = new Excel.ExcelClientContext();
var worksheet = ctx.workbook.worksheets.add(wSheetName);
ctx.load(worksheet);
ctx.executeAsync().then(function () {
	Console.log(worksheet.name);
});
```
[Back](#methods)

### getActiveWorksheet()

Gets the currently active worksheet in the workbook.

#### Syntax
```js
worksheetCollection.getActiveWorksheet();
```
#### Parameters

None

#### Returns

[Worksheet](worksheet.md) object.

#### Examples 

```js
var ctx = new Excel.ExcelClientContext();
var activeWorksheet = ctx.workbook.worksheets.getActiveWorksheet();
ctx.load(activeWorksheet);
ctx.executeAsync().then(function () {
		Console.log(activeWorksheet.name);
});
```
[Back](#methods)

### getItem(param: string)

Gets a worksheet object by name or id.

#### Syntax
```js
worksheetCollection.getItem(param);
```

#### Parameters

Parameter       | Type  | Description
--------------- | ------ | ------------
 `param`| String | Required. The name or id of the worksheet. 

#### Returns

[Worksheet](worksheet.md) object.

#### Examples
```js
var ctx = new Excel.ExcelClientContext();
var wSheetName = 'Sheet1';
var worksheet = ctx.workbook.worksheets.getItem(wSheetName);
ctx.executeAsync().then(function () {
		Console.log(worksheet.index);
});
```
[Back](#methods)


### getItemAt(index: number)

Gets a worksheet object based on its position in the items[] array. 

#### Syntax
```js
worksheetCollection.getItemAt(index);
```

#### Parameters

Parameter       | Type  | Description
--------------- | ------ | ------------
 `index`| Number | Required. The index or position in the items[] array. Zero-indexed.

#### Returns

[Worksheet](worksheet.md) object.

#### Examples
```js
var ctx = new Excel.ExcelClientContext();
var lastPosition = ctx.workbook.worksheets.count - 1;
var worksheet = ctx.workbook.worksheets.getItemAt(lastPosition);
ctx.executeAsync().then(function () {
		Console.log(worksheet.name);
});
```
[Back](#methods)


### Get Worksheet Collection

Get properties of the worksheet collection. 

#### Syntax
```js
workbookObject..worksheets.property;
```

#### Properties

| Property         | Type    |Description|Notes |
|:-----------------|:--------|:----------|:-----|
|`count`| Number   | Number of objects in the collection.|Worksheets.count|
|`items`| [Worksheet](worksheet.md) Array | A collection of all the worksheet objects that are part of the workbook|[Worksheets.item] |


#### Returns

[Worksheet](worksheet.md) collection. 

#### Examples

```js
var ctx = new Excel.ExcelClientContext();
var worksheets = ctx.workbook.worksheets;
ctx.load(worksheets);
ctx.executeAsync().then(function () {
	for (var i = 0; i < worksheets.items.length; i++)
	{
		Console.log(worksheets.items[i].name);
		Console.log(worksheets.items[i].index);
	}
});
```

##### Getting the number of worksheets

```js
var ctx = new Excel.ExcelClientContext();
var worksheets = ctx.workbook.worksheets;
ctx.load(tables);
ctx.executeAsync().then(function () {
	Console.log("Worksheets: Count= " + worksheets.count);
});

```
[Back](#properties)