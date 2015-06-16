# TableRow
Represents a row in a table. 

## [Properties](#get-table-row)

| Property         | Type    |Description|Notes |
|:-----------------|:--------|:----------|:-----|
| `index`          |  Number | Returns the index number of the row within the rows collection of the table. Zero-indexed.| ListRow.Index|
| `values`         | Array (Primitive)  | Returns or sets the unformatted values in the column. |Collection of ListRow.Range.Value2|

## Relationships
The TableRow has the following relationships defined:

| Relationships    | Type    |Description|Notes |
|:-----------------|:--------|:----------|:-----|
| `range`  | [Range](range.md) Object |Returns a Range object associated with the table row.|ListRow.Range|

## Methods
The TableRow has the following methods defined:

| Method     | Return Type    |Description|Notes  |
|:-----------------|:--------|:----------|:------|
|[delete()](#delete)| void     |Deletes the row. ||
|[getRange()](#getrange)| [Range](range.md) Object     | Returns the range object associated with the row.||


## API Specification 

### delete()  

Deletes the row from the table.

#### Syntax

```js
tableRowObject.delete();
```
#### Parameters 
None

#### Returns
Nothing

#### Example 

```js
var tableName = 'Table1';
var ctx = new Excel.ExcelClientContext();
var row = ctx.workbook.tables.getItem(tableName).tableRows.getItemAt(2);
row.delete();
ctx.executeAsync().then();
```

[Back](#methods)

### getRange() 

Returns the range object associated with the row.

#### Syntax
```js
tableRowObject.getRange();
```
#### Parameters

None

#### Returns

[Range](range.md) object.

#### Examples

```js
var tableName = 'Table1';
var ctx = new Excel.ExcelClientContext();
var row = ctx.workbook.tables.getItem(tableName).tableRows.getItemAt(0);
var rowRange = row.getRange();
ctx.load(rowRange);
ctx.executeAsync().then(function () {
	Console.log(rowRange.address);
});
```
[Back](#methods)

### Get Table Row 

Get Table Row's data and properties  

#### Syntax
```js
tableRowsCollection.getItem(index);
```

#### Parameters

Parameter       | Type  | Description
--------------- | ------ | ------------
 `index`| Number | The row index of the row that you wish to get. Zero-indexed.

#### Returns

[Table Row](tableRow.md) object.

#### Examples

```js
var tableName = 'Table1';
var ctx = new Excel.ExcelClientContext();
var row = ctx.workbook.tables.getItem(tableName).tableRows.getItem(0);
ctx.load(row);
ctx.executeAsync().then(function () {
	Console.log(row.index);
});
```
[Back](#properties)

### Update Table Row 

Update values of table row.

#### Syntax
```js
tableRowObject.values = new-values
```
New-values is a 2-D array values of the table row 

#### Example
```js
var ctx = new Excel.ExcelClientContext();
var tables = ctx.workbook.tables;
var newValues = [["New", "Values", "For", "New", "Row"]];
var row = ctx.workbook.tables.getItem(tableName).tableRows.getItemAt(2);
row.values = newValues;
ctx.load(row);
ctx.executeAsync().then(function () {
	Console.log(row.values);
});
```
[Back](#properties)