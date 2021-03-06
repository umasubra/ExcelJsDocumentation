# Table Collection

A collection of all the table objects that are part of the workbook. 

## [Properties](#get-table-collection)

| Property         | Type    |Description|Notes |
|:-----------------|:--------|:----------|:-----|
|`count`| Number   | Number of objects in the collection.|ListObjects.count|
|`items`| [Table](table.md) Array | A collection of all the table objects that are part of the workbook|[ListObjects.item] |

## Relationships

None

## Methods

The table collection has the following methods defined:

| Method     | Return Type    |Description|Notes  |
|:-----------------|:--------|:----------|:------|
|[add(address: string, hasHeaders: bool)](#addaddress-string-hasheaders-bool)| [Table](table.md) Object | Creates a new table.||
|[getItem(name: string)](#getitemname-string)| [Table](table.md) Object      |Retrieve a table object using its name||
|[getItemAt(index: number)](#getitematindex-number)| [Table](table.md) Object     |Retrieve a table based on its position in the items[] array.||

## API Specification 

### add(address: string, hasHeaders: bool)

Create a New Table object. The range source address determines the worksheet under which the table will be added. 

#### Syntax
```js
tableCollection.add(name, rangeSource, containsHeader, showTotals, tableStyle);
```
#### Parameters 

|Parameter       | Type   | Description
|--------------- | ------ | ------------
|`name`  | String | Optional. String value representing the name of the Table.
|`rangeSource`| String | Required. Address or name of the Range object representing the data source.
|`containsHeader` | Boolean | Optional. Boolean value that indicates whether the data being imported has column labels. If the Source does not contain headers (i.e,. when this property set to `false`), Excel will automatically generate headers. If this property value is not set, Excel will determine the header row on its own.
|`showTotals` | Boolean| Optional. Boolean to indicate whether the Total row is visible. This value can be set to show or remove the total row. By default this will be set to `false` 
|`tableStyle` | String | Optional. Constant that represents the Table style. Possible values include: `Light1` thru `Light21`, `Medium1` thru `Medium28`, `Dark1` thru `Dark11`. Excel determines the default style if one is not specified. 

#### Returns
[Table](table.md) object.

#### Example
```js
var ctx = new Excel.ExcelClientContext();
var table = ctx.workbook.tables.add('Sheet1!A1:E7', true);
ctx.load(table);
ctx.executeAsync().then(function () {
	Console.log(table.name);
});

```


[Back](#methods)

### getItem(name: string)

Get table object properties based on name.

#### Syntax
```js
tableCollection.getItem(name);
```

#### Parameters

Parameter       | Type  | Description
--------------- | ------ | ------------
 `name`| String | Required. table name. 

#### Returns

[table](table.md) object.

#### Examples
```js
var ctx = new Excel.ExcelClientContext();
var tableName = 'Table1';
var table = ctx.workbook.tables.getItem(tableName);
ctx.executeAsync().then(function () {
		Console.log(table.index);
});
```
[Back](#methods)


### getItemAt(index: number)

Get table object properties based on its position in the items[] array. 

#### Syntax
```js
tableCollection.getItemAt(index);
```

#### Parameters

Parameter       | Type  | Description
--------------- | ------ | ------------
 `index`| Number | Required. Index or position in the items[]. Zero indexed.

#### Returns

[table](table.md) object.

#### Examples
```js
var ctx = new Excel.ExcelClientContext();
var table = ctx.workbook.tables.getItemAt(0);
ctx.executeAsync().then(function () {
		Console.log(table.name);
});
```
[Back](#methods)

### Get table Collection

Get properties of the table collection. 

#### Syntax
```js
tableCollection.property;
```

#### Properties

| Property         | Type    |Description|Notes |
|:-----------------|:--------|:----------|:-----|
|`count`| Number   | Number of objects in the collection.|tables.count|
|`items`| Object[] | A collection of all the table objects that are part of the workbook|[tables.item] |


#### Returns

[table](table.md) collection. 

#### Examples

```js
var ctx = new Excel.ExcelClientContext();
var tables = ctx.workbook.tables;
ctx.load(tables);
ctx.executeAsync().then(function () {
	for (var i = 0; i < tables.items.length; i++)
	{
		Console.log(tables.items[i].name);
	}
});
```

##### Getting the number of tables

```js
var ctx = new Excel.ExcelClientContext();
var tables = ctx.workbook.tables;
ctx.load(tables);
ctx.executeAsync().then(function () {
	Console.log("tables: Count= " + tables.count);
});

```
[Back](#properties)