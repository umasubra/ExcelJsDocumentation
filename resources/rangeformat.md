# Range Format

Provides access to the Office Art formatting for the range.

## [Properties](#get-range-format)
| Property         | Type    |Description|Notes |
|:-----------------|:--------|:----------|:-----|
|`horizontalAlignment`    | String  |Returns or sets the horizontal alignment for the range. Possible values are: `General`, `Fill`, `CenterAcrossSelection`, `Center`, `Distributed`, `Justify`, `Left`, `Right`. A return value of `null` indicates that the entire range doesn't have a uniform horizontal alignment.|Range.HorizontalAlignment|
|`verticalAlignment`    | String  |Returns or sets the vertical alignment for the range. Possible values are: `Bottom`, `Center`, `Distributed`, `Justify`, `Top`. A return value of `null` indicates that the entire range doesn't have a uniform vertical alignment.|Range.VerticalAlignment|
|`wrapText`    | Boolean  |Returns or sets a boolean that indicates if Excel should wrap the text in the range. A return value of `null` indicates that the entire range doesn't have a uniform wrap setting. |Range.WrapText|


## Relationships
| Property         | Type    |Description|Notes |
|:-----------------|:--------|:----------|:-----|
|`borders`         |[Range Border collection](rangebordercollection.md)|Represents a collection of border objects that apply to the range. |Range.Borders|
|`font`            |[Range Font](rangefont.md) Object                |Represents the font object defined on the range. |Range.Font|
|`fill`      |[Range Fill](rangefill.md) Object    |Represents the fill object defined on the range.|Range.Interior||

## Methods

None

## API Specification 

### Get Range Format 

Gets access to the Office Art formatting for the range.

#### Syntax

```js
rangeObject.format;
rangeObject.format.fill;
rangeObject.format.font;
rangeObject.format.borders;
```

#### Returns

* [Range Format](rangeformat.md) object.
* [Range Fill](rangefill.md) object.
* [Range Font](rangefont.md) object.
* [Range Border Collection](rangeborder.md) object.

Note: Depending on the need, you can select one or more of the format objects.

#### Examples

Below example selects all of the range's format properties. 

```js
var sheetName = "Sheet1";
var rangeAddress = "F:G";
var ctx = new Excel.ExcelClientContext();
var worksheet = ctx.workbook.worksheets.getItem(sheetName);
var range = worksheet.getRange(rangeAddress);
ctx.load(range, {expand: "fill, borders, font"} );
ctx.executeAsync().then(function() {
	Console.log(range.format.wrapText);
	Console.log(range.format.fill.color);
	Console.log(range.format.font.name);
	Console.log(range.format.borders.getItem('InsideHorizontal').lineStyle;	
});
```
[Back](#properties)

### Set Range Format 

Set the formatting for a range.

#### Syntax
```js
rangeObject.format.property = value;
```
Where, property is one of the following Range's Format properties that can be set. 

#### Properties

[Range Format](rangeformat.md)

| Property         | Type    |Description|
|:-----------------|:--------|:----------| 
|`horizontalAlignment`    | String  |Returns or sets the horizontal alignment for the range. Possible values are: `General`, `Fill`, `CenterAcrossSelection`, `Center`, `Distributed`, `Justify`, `Left`, `Right`. A return value of `null` indicates that the entire range doesn't have a uniform horizontal alignment.|Range.HorizontalAlignment|
|`verticalAlignment`    | String  |Returns or sets the vertical alignment for the range. Possible values are: `Bottom`, `Center`, `Distributed`, `Justify`, `Top`. A return value of `null` indicates that the entire range doesn't have a uniform vertical alignment.|Range.VerticalAlignment|
|`wrapText`    | Boolean  |Returns or sets a boolean that indicates if Excel should wrap the text in the range. A return value of `null` indicates that the entire range doesn't have a uniform wrap setting. |Range.WrapText|   

[Range Font](rangefont.md)

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

[Range fill](rangefill.md)

| Property         | Type    |Description|
|:-----------------|:--------|:----------| 
|`color`|String|Returns or sets the fill color using HTML color code representation. HTML color codes are strings that represents hexadecimal triplets of red, green, and blue values (#RRGGBB). For example, `#FF0000` represents Red. ('255' red, '0' green, and '0' blue) |Conversion from Range.Interior.Color value to html color string|

#### Example
The example below sets font name, fill color and wraps text. 

```js
var sheetName = "Sheet1";
var rangeAddress = "F:G";
var range = ctx.workbook.worksheets.getItem(sheetName).getRange(rangeAddress);
range.format.wrapText = true;
range.format.font.name = 'Times New Roman';
range.format.fill.color = '0000FF';
ctx.executeAsync().then();
```

[Back](#properties)

### Set Range Border 

Sets the border to a range and sets the Color, LineStyle, and Weight properties for the new border.

#### Syntax
```js
rangeObject.format.borders(sideIndex).property = value;
```
Where, property is one of the following Range's border properties that can be set. 

#### Properties

Property       | Type   | Description
--------------- | ------ | ------------
|lineStyle| String | Returns or sets the line style for the border. Possible values are: `Continuous`: Continuous line, `Dash`: Dashed line, `DashDot`: Alternating dashes and dots, `DashDotDot`: Dash followed by two dots, `Dot`: Dotted line, `Double`: Double line, `None`: No line, `SlantDashDot`: Slanted dashes.|Border.LineStyle|
|weight| String | Returns or sets the weight of the border around a range. Possible values are: `Hairline`: Hairline (thinnest border), `Medium`: Medium, `Thick`: Thick (widest border), `Thin`: Thin.|Border.Weight|
|color| String | Returns or sets the color of the border line using HTML color code representation. |Border.Color's representation in HTML color code.|.


**sideIndex values:**

`sideIndex` values | Type  | Description
--------------- | ------ | ------------
`DiagonalDown`  |String |Border running from the upper left-hand corner to the lower right of each cell in the range. 
`DiagonalUp`    |String |Border running from the lower left-hand corner to the upper right of each cell in the range.
`EdgeBottom`    |String |Border at the bottom of the range.
`EdgeLeft`      |String |Border at the left-hand edge of the range.
`EdgeRight`     |String |Border at the right-hand edge of the range.
`EdgeTop`       |String |Border at the top of the range.
`InsideHorizontal` |String|Horizontal borders for all cells in the range except borders on the outside of the range.
`InsideVertical`|String |Vertical borders for all the cells in the range except borders on the outside of the range.

#### Example
The example below adds grid border around the range.

```js
var sheetName = "Sheet1";
var rangeAddress = "F:G";
var range = ctx.workbook.worksheets.getItem(sheetName).getRange(rangeAddress);
range.format.borders('InsideHorizontal').lineStyle = 'Continuous';
range.format.borders('InsideVertical').lineStyle = 'Continuous';
range.format.borders('EdgeBottom').lineStyle = 'Continuous';
range.format.borders('EdgeLeft').lineStyle = 'Continuous';
range.format.borders('EdgeRight').lineStyle = 'Continuous';
range.format.borders('EdgeTop').lineStyle = 'Continuous';
ctx.executeAsync().then();
```
[Back](#properties)
