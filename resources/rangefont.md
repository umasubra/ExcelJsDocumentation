# Range Font

Represents the font attributes (font name, font size, color, and so on) for a range.

## [Properties](#get-range-font)

| Property         | Type    |Description|Notes |
|:-----------------|:--------|:----------|:-----|
|`name`|String|Returns or sets the name of the font. For example, `Calibri`.||
|`size`|number|Returns or sets the size of the font. For example, 11.||
|`color`|String|Returns or sets the text color using HTML color code representation. HTML color codes are strings that represents hexadecimal triplets of red, green, and blue values (#RRGGBB). For example, `#FF0000` represents Red. ('255' red, '0' green, and '0' blue). ||
|`italic`|Boolean|Returns or sets a boolean that represents the bold status of italic. True if the font style is italic.||
|`bold`|Boolean|Returns or sets a  boolean that represents the bold status of the font. True if the font is bold. ||
|`strikethrough`|Boolean| Returns or sets a boolean. True if the font is struck through with a horizontal line. False by default.|Range.Font.Strikethrough|
|`subscript`|Boolean|Returns or sets a boolean. True if the font is formatted as subscript. False by default.|Range.Font.Subscript|
|`superscript`|Boolean|Returns or sets a boolean. True if the font is formatted as superscript. False by default.|Range.Font.Superscript  |
|`underline`|Boolean|Returns or sets the type of underline applied to the font. Can be one of the following constants: `None`, `Single`, `Double`, `SingleAccounting`, `DoubleAccounting`||

## Relationships
None

## Methods

None

## API Specification

### Get Range Font 

Gets the font attributes (font name, font size, color, and so on) for a range

#### Syntax

```js
rangeObject.format.font;
```

#### Returns

* [Range Fill](rangefill.md) object.


#### Examples

```js
var sheetName = "Sheet1";
var rangeAddress = "F:G";
var ctx = new Excel.ExcelClientContext();
var worksheet = ctx.workbook.worksheets.getItem(sheetName);
var range = worksheet.getRange(rangeAddress);
var rangeFont = ramge.format.font;
ctx.load(rangeFont);
ctx.executeAsync().then(function() {
	Console.log(rangeFont.name);
});
```
[Back](#properties)

### Set Range Font 

Sets the font formatting for a range.

#### Syntax
```js
rangeObject.format.font.property = value;
```
Where, property is one of the following properties that can be set. 

#### Properties

| Property         | Type    |Description| 
|:-----------------|:--------|:----------|
|`name`|String|Returns or sets the name of the font. For example, `Calibri`.||
|`size`|number|Returns or sets the size of the font. For example, 11.||
|`color`|String|Returns or sets the text color using HTML color code representation. HTML color codes are strings that represents hexadecimal triplets of red, green, and blue values (#RRGGBB). For example, `#FF0000` represents Red. ('255' red, '0' green, and '0' blue). ||
|`italic`|Boolean|A boolean that represents the bold status of italic. True if the font style is italic.||
|`bold`|Boolean|A boolean that represents the bold status of the font. True if the font is bold. ||
|`strikethrough`|Boolean| True if the font is struck through with a horizontal line. False by default.|Range.Font.Strikethrough|
|`subscript`|Boolean|True if the font is formatted as subscript. False by default.|Range.Font.Subscript|
|`superscript`|Boolean|True if the font is formatted as superscript. False by default.|Range.Font.Superscript  |
|`underline`|Boolean|Returns or sets the type of underline applied to the font. Can be one of the following constants: `None`, `Single`, `Double`, `SingleAccounting`, `DoubleAccounting`||

#### Example
The example below sets the font name. 

```js
var sheetName = "Sheet1";
var rangeAddress = "F:G";
var range = ctx.workbook.worksheets.getItem(sheetName).getRange(rangeAddress);
range.format.font.name = 'Times New Roman';
ctx.executeAsync().then();
```
[Back](#properties)
