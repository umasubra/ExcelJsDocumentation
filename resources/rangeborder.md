
# Range Border

Represents a border of a range. 

## Properties
| Property         | Type    |Description|Notes |
|:-----------------|:--------|:----------|:-----|
|sideIndex| String | Returns which side of the range the border is in. Possible values are:  `DiagonalDown`, `DiagonalUp`, `EdgeBottom`, `EdgeLeft`, `EdgeRight`, `EdgeTop`, `InsideHorizontal`, `InsideVertical`.| String values derived from xlBordersIndex constants|
|style| String | Returns or sets the line style for the border. Possible values are: `Continuous`: Continuous line, `Dash`: Dashed line, `DashDot`: Alternating dashes and dots, `DashDotDot`: Dash followed by two dots, `Dot`: Dotted line, `Double`: Double line, `None`: No line, `SlantDashDot`: Slanted dashes.|Border.LineStyle|
|weight| String | Returns or sets the weight of the border around a range. Possible values are: `Hairline`: Hairline (thinnest border), `Medium`: Medium, `Thick`: Thick (widest border), `Thin`: Thin.|Border.Weight|
|color| String | Returns or sets the color of the border line using HTML color code representation. |Border.Color's representation in HTML color code.|


**sideIndex values:**

`sideIndex` values |Description
|`InsideHorizontal`|Horizontal borders for all cells in the range except borders on the outside of the range.|
|`InsideVertical`  |Vertical borders for all the cells in the range except borders on the outside of the range.|
|`DiagonalDown`    |Border running from the upper left-hand corner to the lower right of each cell in the range.|
|`DiagonalUp`      |Border running from the lower left-hand corner to the upper right of each cell in the range.|
|`EdgeBottom`      |Border at the bottom of the range.|
|`EdgeLeft`        |Border at the left-hand edge of the range.|
|`EdgeRight`       |Border at the right-hand edge of the range.|
|`EdgeTop`         |Border at the top of the range.|


## Relationships
None

## Methods
None


