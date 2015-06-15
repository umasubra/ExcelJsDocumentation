# Binding
Represents a binding that is defined in the workbook. 

## [Properties](#get-binding)

| Property       | Type    |Description|Notes |
|:---------------|:--------|:----------|:-----|
|`id`   | String | Returns the name of the binding that was specified at the time of its definition. | Read-only.   |       
|`type`| String |Returns the type of the binding. Can be `Table`,`Range` or `Text`. | Read-only. |


## Relationships
None.    

## Methods

| Method     | Return Type    |Description|Notes  |
|:-----------------|:--------|:----------|:------|
|[getRange()][getrange-link]| [Range](range.md) object |Returns the range represented by the binding.| |
|[getTable()][gettable-link]| [Table](table.md) object |Returns the table represented by the binding.| |  
|[getText()][gettext-link]| String |Returns the text represented by the binding.| |  

### getRange()

Gets the Range object represented by the binding. The range can be a single cell or a range of cells. 

#### Syntax

```js
bindingObject.getRange();
```
#### Parameters
None.

#### Returns

[Range](range.md) object.

#### Examples


```js
var ctx = new Excel.ExcelClientContext();
var binding = ctx.workbook.bindings.getItemAt(0);
var range = binding.getRange();
ctx.load(range);
ctx.executeAsync().then(function() {
	Console.log(range.cellCount);
});
```

[Back](#methods)

### getTable()

Gets the Table object represented by the binding. 

#### Syntax
```js
bindingObject.getTable();
```
#### Parameters

None

#### Returns

[Table](table.md) object.

#### Examples

```js
var ctx = new Excel.ExcelClientContext();

var binding = ctx.workbook.bindings.getItemAt(0);
var table = binding.getTable();
ctx.load(table);
ctx.executeAsync().then(function () {
		Console.log(table.name);
});
```
[Back](#methods)

### getText()

Gets the text represented by the binding.

#### Syntax

```js
bindingObject.getText();
```
#### Parameters
None.

#### Returns
String.

#### Examples

```js
var ctx = new Excel.ExcelClientContext();
var binding = ctx.workbook.bindings.getItemAt(0);
var text = binding.getText();
ctx.load(text);
ctx.executeAsync().then(function() {
	Console.log(text);
});
```

[Back](#methods)

### Get Binding

Get the properties of the Binding object. 

#### Syntax

```js
bindingObject.type;
```
#### Properties
| Property       | Type    |Description|Notes |
|:---------------|:--------|:----------|:-----|
|`id`   | String | Returns the name of the binding that was specified at the time of its definition. | Read-only.   |       
|`type`| String |Returns the type of the binding. Can be `Table`,`Range` or `Text`. | Read-only. |


#### Returns

[Binding](binding.md) object.

#### Examples

```js
var ctx = new Excel.ExcelClientContext();
var binding = ctx.workbook.bindings.getItemAt(0);
ctx.load(binding);
ctx.executeAsync().then(function() {
	Console.log(binding.type);
});
```

[Back](#properties)




[getrange-link]: #getrange
[gettable-link]: #gettable
[gettext-link]: #gettext
