# Reference Collection
Represents a collection of temporary references to ranges, used and managed by Office add-ins.

## Properties
None.

## Relationships

None

## Methods

The Reference collection has the following methods defined:

| Method     | Return Type    |Description|Notes  |
|:-----------------|:--------|:----------|:------|
|[add(rangeObject: Range)](#addrangeobject-range)| Null             |Creates a new reference on a range.  ||
|[remove(rangeObject: Range)](#removerangeobject-range)| Null             |Remove a reference to a range from the collection.  ||


## API Specification 

### add(rangeObject: range)
Adds a reference to a range to the reference collection. 

#### Syntax
```js
referenceCollection.add(rangeObject);
```

#### Parameters

Parameter       | Type   | Description
--------------- | ------ | ------------
`rangeObject`  | [Range](range.md)| The Range object to be added to the reference collection.

#### Returns
Null

#### Examples

```js
var sheetName = "Sheet1";
var rangeAddress = "A1:B2";
var ctx = new Excel.ExcelClientContext();
var range = ctx.workbook.worksheets.getItem(sheetName).getRange(rangeAddress);
ctx.references.add(range);
ctx.load(range);

ctx.executeAsync().then(function () {
	range.insert("Down");
	Console.log(range.address); // Address should be updated to A3:B4
	ctx.executeAsync().then();
});
```
[Back](#methods)

### remove(rangeObject: range)

Removes a reference from the collection. 

#### Syntax
```js
referenceCollection.remove(rangeObject);
```

#### Parameters

Parameter       | Type   | Description
--------------- | ------ | ------------
`rangeObject`  | [Range](range.md)| The Range object to be removed from the reference collection.

#### Returns
Null

#### Examples

```js
```js
var sheetName = "Sheet1";
var rangeAddress = "A1:B2";
var ctx = new Excel.ExcelClientContext();
var range = ctx.workbook.worksheets.getItem(sheetName).getRange(rangeAddress);
ctx.references.add(range);
ctx.load(range);

ctx.executeAsync().then(function () {
	range.insert("Down");
	Console.log(range.address); // Address should be updated to A3:B4
	ctx.references.remove(range); 
	ctx.executeAsync().then();
});
```
[Back](#methods)

