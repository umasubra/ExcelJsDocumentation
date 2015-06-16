# Table
Represents a collection of organized cells designed to make management of the data easy.

## [Properties](#get-table)

| Property         | Type    |Description|Notes |
|:-----------------|:--------|:----------|:-----|
| `id`  |  Number | Returns the unique key that identifies the table in a workbook. Note: If the table gets deleted, Excel workbook could reuse the id value for another table.   |        |
| `name`       | String| Returns or sets the name of the table. | ListObject.Name |
| `showHeaders` | Boolean| Returns or sets a boolean to indicate whether the header row should be visible or not. This value can be set to show or remove the header row.| ListObject.ShowHeaders|
| `showTotals` | Boolean| Returns or sets a boolean to indicate whether the totals row should be visible or not. This value can be set to show or remove the totals row.| ListObject.ShowTotals|
| `style` | String | Returns or sets the table style. Possible values are: `Light1` thru `Light21`, `Medium1` thru `Medium28`, `StyleDark1` thru `StyleDark11`.|ListObject.TableStyle|

## Relationships
The Table object has the following relationships defined:

| relationships    | Type    |Description|Notes |
|:-----------------|:--------|:----------|:-----|
| columns  | [TableColumn collection](tablecolumncollection.md)       |Represents a collection of all the columns in the table. |ListObject.TableColumns  |          
| rows      | [TableRow collection](tablerowcollection.md)         |Represents a collection of all the rows in the table. |ListObject.ListRows      |

## Methods

The Table object has the following methods defined:

| Method     | Return Type    |Description|Notes  |
|:-----------------|:--------|:----------|:------|
|[delete()](#delete)| void     |Deletes the table. ||
|[getHeaderRowRange()](#getheaderrowrange) | [Range](range.md) object |Gets the Range object associated with the header row of the table.||
|[getDataBodyRange()](#getdatabodyrange) | [Range](range.md) object |Gets the Range object associated with the body of the table.  ||
|[getRange()](#getrange) | [Range](range.md) object |Gets the Range object associated with the entire table. ||
|[getTotalRowRange()](#gettotalrowrange) | [Range](range.md) object |Gets the Range object associated with the totals row of the table. ||

## API Specification 

### delete()

Deletes the table and clears the cell data from the table.

#### Syntax
```js
tableObject.delete();
```

#### Parameters 
None

#### Returns
Nothing

#### Example 

```js
var tableName = 'Table1';
var ctx = new Excel.ExcelClientContext();
var table = ctx.workbook.tables.getItem(tableName);
table.delete();
ctx.executeAsync().then();
```
[Back](#methods)

### getHeaderRowRange()

Gets the Range object associated with the header row of the table.

#### Syntax
```js
tableObject.delete();
```

#### Parameters 
None

#### Returns
Nothing

#### Example 

```js
var tableName = 'Table1';
var ctx = new Excel.ExcelClientContext();
var table = ctx.workbook.tables.getItem(tableName);
table.delete();
ctx.executeAsync().then();
```
[Back](#methods)


### getDataBodyRange()

Gets the Range object associated with the body of the table. 

#### Syntax
```js
tableObject.getDataBodyRange();
```

#### Parameters

None

#### Returns

[Range](range.md) object.


#### Examples

```js
var tableName = 'Table1';
var ctx = new Excel.ExcelClientContext();
var table = ctx.workbook.tables.getItem(tableName);
var tableDataRange = table.getDataBodyRange();
ctx.executeAsync().then(function () {
		Console.log(tableDataRange.address);
});
```
[Back](#methods)

### getRange()

Gets the Range object associated with the entire table.

#### Syntax
```js
tableObject.getRange();
```

#### Parameters

None

#### Returns

[Range](range.md) object.


#### Examples

```js
var tableName = 'Table1';
var ctx = new Excel.ExcelClientContext();
var table = ctx.workbook.tables.getItem(tableName);
var tableRange = table.getRange();
ctx.executeAsync().then(function () {
		Console.log(tableRange.address);
});
```

[Back](#methods)
### getTotalRowRange()

Gets the Range object associated with the totals row of the table.

#### Syntax
```js
tableObject.getTotalRowRange();
```

#### Parameters

None

#### Returns

[Range](range.md) object.

#### Examples

```js
var tableName = 'Table1';
var ctx = new Excel.ExcelClientContext();
var table = ctx.workbook.tables.getItem(tableName);
var tableTotalsRange = table.getTotalRowRange();
ctx.executeAsync().then(function () {
		Console.log(tableTotalsRange.address);
});
```
[Back](#methods)


### Get Table

Gets the table by name.

#### Syntax

```js
tableCollection.getItem(name);
```

#### Parameters

Parameter        | Type   | Description
---------------  | ------ | ------------
 `name`| String  | Required. The name of the table. 

#### Syntax
```js
tableCollection.getItemAt(index);
```

#### Parameters

Parameter        | Type   | Description
---------------  | ------ | ------------
 `index`| Number | Required. The index of the table in the tables collection. Zero-indexed.

#### Returns

[Table](table.md) object. 

#### Examples

##### Getting a table by name

```js
var ctx = new Excel.ExcelClientContext();
var tableName = 'Table1';
var table = ctx.workbook.tables.getItem(tableName);
ctx.executeAsync().then(function () {
		Console.log(table.index);
});
```
##### Getting a table by index

```js
var ctx = new Excel.ExcelClientContext();
var index = 0;
var table = ctx.workbook.tables.getItemAt(0);
ctx.executeAsync().then(function () {
		Console.log(table.name);
});
```
[Back](#properties)

### Update Table

This API allows setting of Table properties such as name and show totals. In order to update the table content, use the update table row or column API.

#### Syntax
```js
tableObject.property = 'new-value';
```

#### Properties 

Following properties can be updated directly. 

|Property      | Type   | Description      |
|-------------- | ------ | -----------------|
| `name`       | String| Returns or sets the name of the table. | ListObject.Name |
| `showHeaders` | Boolean| Returns or sets a boolean to indicate whether the header row should be visible or not. This value can be set to show or remove the header row.| ListObject.ShowHeaders|
| `showTotals` | Boolean| Returns or sets a boolean to indicate whether the totals row should be visible or not. This value can be set to show or remove the totals row.| ListObject.ShowTotals|
| `style` | String | Returns or sets the table style. Possible values are: `Light1` thru `Light21`, `Medium1` thru `Medium28`, `StyleDark1` thru `StyleDark11`.|ListObject.TableStyle|

#### Example 

```js
var tableName = 'Table1';
var ctx = new Excel.ExcelClientContext();
var table = ctx.workbook.tables.getItem(tableName);
table.name = 'Table1-Renamed';
table.showTotals = false;
table.tableStyle = 'TableStyleMedium2';
ctx.load(table);
ctx.executeAsync().then(function () {
		Console.log(table.tableStyle);
});
```
[Back](#properties)

