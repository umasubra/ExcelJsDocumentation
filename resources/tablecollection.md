# Table Collection

Represents a collection of all the tables that are part of the workbook. 

## [Properties](#get-table-collection)

| Property         | Type    |Description|Notes |
|:-----------------|:--------|:----------|:-----|
|`count`| Number   | Returns the number of bindings in the collection.|ListObjects.count|
|`items`| [Table](table.md) array | Returns a collection of all the tables that are part of the workbook.|[ListObjects.item] |

## Relationships

None

## Methods

The table collection has the following methods defined:

| Method     | Return Type    |Description|Notes  |
|:-----------------|:--------|:----------|:------|
|[add(address: string, hasHeaders: bool)](#addaddress-string-hasheaders-bool)| [Table](table.md) Object | Creates a new table.||
|[getItem(name: string)](#getitemname-string)| [Table](table.md) Object      |Gets a table by name.||
|[getItemAt(index: number)](#getitematindex-number)| [Table](table.md) Object     |Gets a table based on its position in the items[] array.||

## API Specification 

### add(address: string, hasHeaders: bool)

Create a new table. The range source address determines the worksheet under which the table will be added. 

#### Syntax
```js
tableCollection.add(name, rangeSource, containsHeader, showTotals, tableStyle);
```
#### Parameters 

|Parameter       | Type   | Description
|--------------- | ------ | ------------
|`name`  | String | Optional. The name of the table.|
|`rangeSource`| String | Required. The address or name of the range that is the data source for the table.|
|`containsHeader` | Boolean | Optional. A boolean that indicates whether the data being imported has column headers. If the source does not contain headers (that is, when this property set to `false`), Excel will automatically generate headers. If this property is not set, Excel will determine the header row on its own.|
|`showTotals` | Boolean| Optional. A boolean that indicatea whether the totals row is visible. This value can be set to show or remove the total row. By default, this will be set to `false` . |
|`tableStyle` | String | Optional. The table style. Possible values are: `Light1` thru `Light21`, `Medium1` thru `Medium28`, `Dark1` thru `Dark11`. Excel determines the default style if one is not specified. |

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

Gets the table by name.

#### Syntax
```js
tableCollection.getItem(name);
```

#### Parameters

Parameter       | Type  | Description
--------------- | ------ | ------------
 `name`| String | Required. The table name. 

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

Gets the table based on its position in the items[] array. 

#### Syntax
```js
tableCollection.getItemAt(index);
```

#### Parameters

Parameter       | Type  | Description
--------------- | ------ | ------------
 `index`| Number | Required. The Index or position in the items[] array. Zero-indexed.

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

Gets the table collection. 

#### Syntax
```js
tableCollection.property;
```

#### Properties

| Property         | Type    |Description|Notes |
|:-----------------|:--------|:----------|:-----|
|`count`| Number   | Returns the number of bindings in the collection.|ListObjects.count|
|`items`| [Table](table.md) array | Returns a collection of all the tables that are part of the workbook.|[ListObjects.item] |


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