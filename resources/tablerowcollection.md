# tablerow Collection
Represents a collection of all the rows that are part of the table.

## [Properties](#get-tablerow-collection)

| Property         | Type    |Description|Notes |
|:-----------------|:--------|:----------|:-----|
|`count`| Number   | Returns the number of rows in the table.|tablerows.count|
|`items`| [Table Row](tablerow.md) Array | Returns a collection of all the row objects that are part of the table.|[tablerows.item] |

## Relationships

None

## Methods

The tablerow collection has the following methods defined:

| Method     | Return Type    |Description|Notes  |
|:-----------------|:--------|:----------|:------|
<<<<<<< HEAD
|[add(index: number, values: any[][])](#index-number-values-any)| [Table Row](tablerow.md) Object  |Adds a new row to the table.||
|[getItem(name: string)](#getitemname-string)| [Table Row](tablerow.md) Object ||Gets a row object by name.||
=======
|[add(values: any[][], index: number)](#addvalues-any-index-number)| [Table Row](tablerow.md) Object  |Adds a new row to the table. ||
>>>>>>> 8fcb47ff7422ac46ccb364ef484b77e8c5ba109a
|[getItemAt(index: number)](#getitematindex-number)| [Table Row](tablerow.md) Object |Gets a row object based on its position in the items[] array.||

## API Specification 


### add(index: number, values: any[][])

Adds a new row to the table.

#### Syntax
```js
tableRowCollection.add(values, values);
```
#### Parameters 
Parameter       | Type   | Description
--------------- | ------ | ------------
`values` | any[][] | A 2-D array of unformatted values of the table row. 
`index` |  Number |Optional. Specifies the relative position of the new row. If not specified, the addition happens at the end. The previous column at this position is shifted outward to the bottom. Zero-indexed.


#### Returns
[Table Row](tableRow.md) object.

#### Example
```js
var ctx = new Excel.ExcelClientContext();
var tables = ctx.workbook.tables;
var values = [["Sample", "Values", "For", "New", "Row"]];
<<<<<<< HEAD
var row = tables.getItem("Table1").tablerows.add(null, values);
=======
var row = tables.getItem("Table1").rows.add(values, null);
>>>>>>> 8fcb47ff7422ac46ccb364ef484b77e8c5ba109a
ctx.load(row);
ctx.executeAsync().then(function () {
	Console.log(row.index);
});
```
[Back](#methods)

### getItemAt(index: number)

Gets a row object based on its position in the items[] array. 

#### Syntax
```js
tableRowCollection.getItemAt(index);
```

#### Parameters

Parameter       | Type  | Description
--------------- | ------ | ------------
 `index`| Number | Required. The index or position in the items[] array. Zero-indexed.

#### Returns

[tablerow](tablerow.md) object.

#### Examples
```js
var ctx = new Excel.ExcelClientContext();
var tablerow = ctx.workbook.tables.getItem('Table1').rows.getItemAt(0);
ctx.load(tablerow);
ctx.executeAsync().then(function () {
		Console.log(tablerow.name);
});
```
[Back](#methods)

### Get tablerow Collection

Get the properties of the tablerow collection. 

#### Syntax
```js
tableRowCollection.property;
```

#### Properties

| Property         | Type    |Description|Notes |
|:-----------------|:--------|:----------|:-----|
|`count`| Number   | Returns the number of rows in the table.|tablerows.count|
|`items`| [Table Row](tablerow.md) Array | Returns a collection of all the row objects that are part of the table.|[tablerows.item] |


#### Returns

[tablerow](tablerow.md) collection. 

#### Examples

```js
var ctx = new Excel.ExcelClientContext();
var tablerows = ctx.workbook.tables.getItem('Table1').rows;
ctx.load(tablerows);
ctx.executeAsync().then(function () {
	for (var i = 0; i < tablerows.items.length; i++)
	{
		Console.log(tablerows.items[i].index);
	}
});
```

##### Getting the number of tablerows

```js
var ctx = new Excel.ExcelClientContext();
var tablerow = ctx.workbook.tables.getItem('Table1').rows.getItemAt(0);
ctx.load(tablerows);
ctx.executeAsync().then(function () {
	Console.log("tablerows: Count= " + tablerows.count);
});

```
[Back](#properties)
