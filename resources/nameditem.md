# Named Item

Represents a defined name for a range of cells.  Names can be primitive named objects, range object, or a reference to a range. This object can be used to obtain range objects that are associated with names.

## [Properties](#get-named-item)

| Property         | Type    |Description|Notes  |
|:-----------------|:--------|:----------|:-----|
| `name`  | String|Returns the name of the named item.| Name.Name|
| `type` | String|Returns or sets the type of reference associated with the name. Possible values are: `Range`, `String`, `Integer`, `Double`, `Boolean`. | Derived property |
| `value`| String |Returns the formula that the name is defined to refer to. For example, `=Sheet14!$B$2:$H$12`, `=4.75`. | Name.Value|
| `visible` | Boolean |Returns or sets a boolean that determines whether the object is visible. | Name.Visible |

## Relationships
None
     
## Methods

The Worksheet has the following methods defined:

| Method     | Return Type    |Description|Notes  |
|:-----------------|:--------|:----------|:------|
|[getRange()](#getrange)| [Range](range.md) object |Returns the Range object that is associated with the name. Returns `null` if the name is not of the type `Range`.| |

## API Specification 

### getRange()

Returns the Range object that is associated with the name. Returns `null` if the name is not of the type `Range`. 

**Note: This API currently supports only the Workbook scoped items.**

#### Syntax
```js
namedItemObject.getRange(); 
```

#### Parameters
None

#### Returns

[Range](range.md) object.

#### Examples
```js
var ctx = new Excel.ExcelClientContext();
var names = ctx.workbook.names;
var range = names.getItem('MyRange').getRange();
ctx.load(range);
ctx.executeAsync().then(function () {
		Console.log(range.address);
});
```
[Back](#methods)

### Get Named Item

Gets a named object. 

** Note: This API currently supports only the Workbook scoped items. **
#### Syntax
```js
namesCollection.getItem(name);
```

#### Parameters

Parameter       | Type  | Description
--------------- | ------ | ------------
 `name`| String | Required. Returns the name.

#### Returns

[Named-Item](nameditem.md) object.

#### Examples
```js
var ctx = new Excel.ExcelClientContext();
var names = ctx.workbook.names;
var namedItem = names.getItem('MyRange');
ctx.load(namedItem);
ctx.executeAsync().then(function () {
		Console.log(namedItem.type);
});
```
[Back](#properties)
