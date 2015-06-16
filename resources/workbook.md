# Workbook
Represents the top-level object which contains workbook-related objects such as worksheets, tables, ranges, and so on. It can be used to list related references. 

## Properties

None

## Relationships
The Workbook has the following relationships defined:

| Relationship    | Type    |Description|Notes |
|:----------------|:--------|:----------|:-----|
| application  | [Application](application.md)| Represents an object that represents the Excel application that manages the workbook. |
| names       | [NamedItem collection](nameditemCollection.md)| Represents a collection of named ranges associated with the workbook.  |Workbook.Names      |
| tables       | [Table collection](tableCollection.md)        | Represents a collection of tables associated with the workbook.       |Workbook.ListObjects|
| worksheets   | [Worksheet collection](worksheetCollection.md)| Represents a collection of worksheets associated with the workbook.    |Workbook.Worksheets |
| bindings   | [Binding collection](bindingCollection.md)| Represents a collection of all the binding objects that are part of the workbook.    | |

## Methods

The Worksheet has the following methods defined:

| Method     | Return Type    |Description|Notes  |
|:-----------------|:--------|:----------|:------|
|[getSelectedRange()](#getselectedrange)| [Range](range.md) object |Gets the currently selected range from the workbook. | |  

## API Specification 



### getSelectedRange()

Gets the currently selected range from the workbook. 

#### Syntax
```js
workbookObject..getSelectedRange();
```
#### Parameters
None

#### Returns

[Range](range.md) object.

#### Examples

```js
var ctx = new Excel.ExcelClientContext();
var selectedRange = ctx.workbook.getSelectedRange();
ctx.executeAsync().then(function () {
		Console.log(selectedRange.address);
});
```
[Back](#methods)
