# Chart Font

Represents the font attributes (font name, font size, color, and so on) for a chart element. 

## [Properties](#set-font)

| Property         | Type    |Description|Notes |
|:-----------------|:--------|:----------|:-----|
|`name`|String|Returns or sets the name of the font. For example, `Calibri`.||
|`size`|number|Returns or sets the size of the font. For example, 11.||
|`color`|String|Returns or sets the text color using HTML color code representation. HTML color codes are strings that represents hexadecimal triplets of red, green, and blue values (#RRGGBB). For example, `#FF0000` represents Red. ('255' red, '0' green, and '0' blue). ||
|`italic`|Boolean|A boolean that represents the bold status of italic. True if the font style is italic.||
|`bold`|Boolean|A boolean that represents the bold status of the font. True if the font is bold. ||
|`underline`|Boolean|Returns or sets the type of underline applied to the font. Can be one of the following constants: `None`, `Single`, `Double`, `SingleAccounting`, `DoubleAccounting`||

## Relationships
None

## Methods
None.

## API Specification 

### Set Font

Update the font formatting for a chart element.

#### Syntax
Use chart title as an example.
```js
chartObject.title.format.font.name = "Calibri";
chartObject.title.format.font.size = 12;
chartObject.title.format.font.color = "#FF0000";
chartObject.title.format.font.italic =  false;
chartObject.title.format.font.bold = true;
chartObject.title.format.font.underline = false;

```

#### Properties
| Property         | Type    |Description|Notes |
|:-----------------|:--------|:----------|:-----|
|`name`|String|Returns or sets the name of the font. For example, `Calibri`.||
|`size`|number|Returns or sets the size of the font. For example, 11.||
|`color`|String|Returns or sets the text color using HTML color code representation. HTML color codes are strings that represents hexadecimal triplets of red, green, and blue values (#RRGGBB). For example, `#FF0000` represents Red. ('255' red, '0' green, and '0' blue). ||
|`italic`|Boolean|A boolean that represents the bold status of italic. True if the font style is italic.||
|`bold`|Boolean|A boolean that represents the bold status of the font. True if the font is bold. ||
|`underline`|Boolean|Returns or sets the type of underline applied to the font. Can be one of the following constants: `None`, `Single`, `Double`, `SingleAccounting`, `DoubleAccounting`||

#### Returns

[ChartFont](chartFont.md) object. 

#### Examples

##### Set chart title to be Calbri, size 10, bold and in red. 
```js
var ctx = new Excel.ExcelClientContext();
var title = ctx.workbook.worksheets.getItem("Sheet1").charts.getItem("Chart1").title;

title.format.font.name = "Calibri";
title.format.font.size = 12;
title.format.font.color = "#FF0000";
title.format.font.italic =  false;
title.format.font.bold = true;
title.format.font.underline = false;

ctx.executeAsync().then(function () {
		logComment("Chart Title Font Updated");
});
```
[Back](#properties)
