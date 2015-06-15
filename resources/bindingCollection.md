# Binding Collection
Represents the collection of all the [Binding](binding.md) objects that are part of the workbook. 

## [Properties](#get-binding-collection)

| Property         | Type    |Description|Notes |
|:-----------------|:--------|:----------|:-----|
|`count`| Number   | Returns the number of bindings in the collection.| |
|`items`| [Binding](binding.md) array | Returns a collection of all the bindings defined in a workbook.| |

## Relationships
None

## Methods

| Method     | Return Type    |Description|Notes  |
|:-----------------|:--------|:----------|:------|
|[getItem(param: string)](#getitemparam-string)| [Binding](binding.md) object      |Gets a Binding object by id.||
|[getItemAt(index: number)](#getitematindex-number)| [Binding](binding.md) object     |Gets a Binding object based on its position in the items[] array.||


## API Specification 

### getItemAt(index: number)

Gets the Binding object based on its position in the items[] array.

#### Syntax
```js
bindingCollection.getItemAt(index);
```

#### Parameters

Parameter       | Type  | Description
--------------- | ------ | ------------
 `index`| Number | Required. Index or position of the binding in the items[] array. Zero-indexed.

#### Returns

[Binding](binding.md) object.

#### Examples
```js
var ctx = new Excel.ExcelClientContext();
var lastPosition = ctx.workbook.bindings.count - 1;
var binding = ctx.workbook.bindings.getItemAt(lastPosition);
ctx.executeAsync().then(function () {
		Console.log(binding.id);
});
```
[Back](#methods)


### Get Binding Collection

Get the properties of the binding collection. 

#### Syntax
```js
workbookObject..bindings.property;
```

#### Properties

| Property         | Type    |Description|Notes |
|:-----------------|:--------|:----------|:-----|
|`count`| Number   | Returns the number of bindings in the collection.| |
|`items`| [Binding](binding.md) array | Returns a collection of all the Binding objects that are part of the workbook.| |


#### Returns

[Binding](binding.md) collection. 

#### Examples

```js
var ctx = new Excel.ExcelClientContext();
var bindings = ctx.workbook.bindings;
ctx.load(bindings);
ctx.executeAsync().then(function () {
	for (var i = 0; i < bindings.items.length; i++)
	{
		Console.log(bindings.items[i].id);
		Console.log(bindings.items[i].index);
	}
});
```

##### Getting the number of bindings

```js
var ctx = new Excel.ExcelClientContext();
var bindings = ctx.workbook.bindings;
ctx.load(bindings);
ctx.executeAsync().then(function () {
	Console.log("Bindings: Count= " + bindings.count);
});

```
[Back](#properties)