# ASP .NET Core MVC Chart Tag Helper

## Introduction

The Chart is an easy to use charting component which uses W3C standards like HTML5, CSS and SVG. The Chart provides optimal chart rendering performance and high quality visualization across browsers and devices (PCs, Laptops, Tablets and Mobile phones). It automatically detects the browser capabilities and uses SVG or HTML5 rendering with hardware acceleration (when available) in modern browsers (IE9+, Firefox, Chrome, Opera) and VML rendering in IE8 and earlier browsers. The ability to render SVG, HTML5 and VML makes jqxChart an ideal choice for adding charting capabilities in your web sites and applications. No browser plug-ins are required. Try our Chart Studio - cloud solution for visual editing and hosting of interactive charts!


## Highlights

- Optimal rendering across browsers
- Web Standards Compliant
- Runs on mobile, touch devices and PCs
- Optimized for Performance
- Easy to use APIs
- Built-in color palettes
- Data binding to XML, CSV, TSV, JSON, JSONP

## Chart Types

The Chart tag helper supports several common chart types. You can easily plot series of different types on a common chart. A type must be specified for each series group. Currently jqxChart supports the following series:

- column - simple graph with column series
- stackedcolumn - stacked column series
- stackedcolumn100 - percentage stacked columns
- line - simple straight lines connecting the value points
- pie - circular chart divided into sectors, illustrating proportion
- donut - donut charting series
- bar - bar charting series
- candlestick - candlestick financial charting series
- ohlc - ohlc financial graph series
- bubble - data is displayed in a graph as a collection of bubbles
- scatter - data is displayed in a graph as a collection of points
- stackedline - stacked lines
- stackedline100 - percentage stacked lines
- spline - smooth lines connecting the value points
- stackedspline - smooth stacked lines
- stackedspline100 - percentage stacked smooth lines
- polarseries - polar series
- spiderseries - spider series
- area - area connecting the value points with streight lines
- stackedarea- stacked area with streight lines between the points
- stackedline100 - percentage stacked area
- areaspline - smooth area connecting the value points
- stackedareaspline - smooth stacked areas
- stackedareaspline100 - percentage stacked smooth area
- waterfall - waterfall chart

## Chart Demos

[ASP .NET Core MVC Tag Helpers Demos page](http://www.jqwidgets.com/asp.net-core-mvc-tag-helpers/asp.net-core-mvc-chart-tag-helper/index.htm).

## Setup and Installation

### 1. Create a new ASP .NET Core Web Application
![alt text](http://aspcore.jqwidgets.com/bootstrap/tag-helpers/images/aspnetcore-net-project.png "Tag Helpers 1")

![alt text](http://aspcore.jqwidgets.com/bootstrap/tag-helpers/images/aspnetcore-webapplication.png "Tag Helpers 2")

### 2. Reference the Tag Helpers

Install the Tag Helper's Nuget package from https://www.nuget.org/packages/Chart.AspNetCore.Mvc/

### 3. Update _ViewImports.cshtml

```
@using jQWidgets.AspNetCore.Mvc.TagHelpers
@addTagHelper *, Microsoft.AspNetCore.Mvc.TagHelpers
@addTagHelper *, jQWidgets.AspNetCore.Mvc.TagHelpers
@inject Microsoft.ApplicationInsights.Extensibility.TelemetryConfiguration TelemetryConfiguration
```

### 4. Build the Solution

Click Build in the top menu bar of Visual Studio, then click Build Solution to Build the solution


### 5. Add a Tag Helper to a Page

We can now add a Tag Helper to one of the views (pages).
For example, we will add the Tag Helper to Views\Home\About.cshtml.
While typing, IntelliSense suggest the existing Tag Helpers:

```html
@using jQWidgets.AspNetCore.Mvc.TagHelpers;
@model IEnumerable<jQWidgets.AspNet.Core.Models.BrowserShare>
@{
    ViewData["Title"] = "ASP .NET MVC Pie Chart Example";
    Padding padding = new Padding() { Left = 5, Top = 5, Right = 5, Bottom = 5 };
    Padding titlePadding = new Padding() { Left = 0, Top = 0, Right = 0, Bottom = 10 };
    Rectangle legendPosition = new Rectangle() { Left = 520, Top = 140, Width = 100, Height = 100 };
    FormatSettings formatSettings = new FormatSettings() { Sufix = "%", DecimalPlaces = 1 };
}
<label>ASP .NET Core MVC Chart Tag Helper Example</label><br/><br/>
<jqx-chart style="width: 850px; height: 500px;" color-scheme="scheme02" padding="padding" title-padding="titlePadding" title="Desktop browsers share" description="(source: wikipedia.org)" show-legend="false" legend-position="legendPosition" source="Model">
    <jqx-chart-series-groups>
         <jqx-chart-serie-group show-labels="true" type=@SerieType.Pie>
                <jqx-chart-series>
                    <jqx-chart-serie datafield="Share" display-text="Browser" label-radius="120" initial-angle="15" radius="170" center-offset="0" format-settings="formatSettings">
                   </jqx-chart-serie>
                </jqx-chart-series>
         </jqx-chart-serie-group>
    </jqx-chart-series-groups>
</jqx-chart>
```

```jqx-chart-series-groups``` tag helper should be defined within the ```jqx-chart``` tag helper and
defines the Chart series groups collection. ```jqx-chart-serie-group``` tag helper should be
defined within the ```jqx-chart-series-groups``` tag helper and defines a Chart serie group.<br />
```jqx-chart-series``` tag helper should be defined within the ```jqx-chart-serie-group``` tag helper
and defines the Chart series collection. <br />
```jqx-chart-serie``` tag helper should be defined within the ```jqx-chart-series``` tag helper and defines a Chart serie. <br />
The ```for``` and ```radiusFor``` members can be used for model binding. <br />
```jqx-chart-x-axis``` tag helper should be defined within the ```jqx-chart``` tag helper and defines the Chart's X Axis. 
The for member can be used for model binding. <br />
```jqx-chart-value-axis``` tag helper should be defined within the ```jqx-chart``` tag helper and defines the Chart's Value Axis. <br />
```jqx-chart-title``` tag helper should be defined within the ```jqx-chart-value-axis``` tag helper and defines the Chart's Title. <br />
```jqx-chart-labels``` tag helper should be defined within the ```jqx-chart-value-axis``` tag helper and defines the Chart's Labels.<br />
```jqx-chart-range-selector``` tag helper should be defined within the ```jqx-chart``` tag helper and defines the Chart's Range selector.

```html
@model IEnumerable<jQWidgets.AspNet.Core.Models.ChartSalesDataItem>
@using jQWidgets.AspNetCore.Mvc.TagHelpers;
@{
    ViewData["Title"] = "ASP .NET MVC Bubble Chart Example";
    var item = Model.FirstOrDefault();
    Padding padding = new Padding() { Left = 5, Top = 5, Right = 5, Bottom = 5 };
    Padding titlePadding = new Padding() { Left = 90, Top = 0, Right = 0, Bottom = 10 };
    FormatSettings formatSettings = new FormatSettings() { Prefix = "$", ThousandsSeparator="," };
}
<label>ASP .NET MVC Core Bubble Chart Example</label><br/><br/>
<jqx-chart style="width: 850px; height: 500px;" color-scheme="scheme02" show-legend="true" padding="padding" title-padding="titlePadding" title="Sales by City in Q1 and Q2, and YoY sales growth"
     description="(the size of the circles represents relative YoY growth)" source="Model">
    <jqx-chart-x-axis values-on-ticks="false" for="@item.City" ></jqx-chart-x-axis>
    <jqx-chart-value-axis unit-interval="50000" min-value="50000" max-value="350000">
        <jqx-chart-title text="Sales ($)"></jqx-chart-title>
        <jqx-chart-labels horizontal-aligment="HorizontalAlignment.Right" format-settings="formatSettings"></jqx-chart-labels>
    </jqx-chart-value-axis>
    <jqx-chart-series-groups>
        <jqx-chart-serie-group type="SerieType.Bubble">
            <jqx-chart-series>
                <jqx-chart-serie for="@item.SalesQ1" radius-for="@item.YoYGrowthQ1" min-radius="10" max-radius="30" display-text="Sales in Q1"></jqx-chart-serie>
                <jqx-chart-serie for="@item.SalesQ2" radius-for="@item.YoYGrowthQ2" min-radius="10" max-radius="30" display-text="Sales in Q2"></jqx-chart-serie>
            </jqx-chart-series>
        </jqx-chart-serie-group>
    </jqx-chart-series-groups>
</jqx-chart>
``` 

## License

Free for non-commercial purposes. For commercial usage, please visit http://www.jqwidgets.com/license/.

## Any questions, comments or additions?

If you have a feature request or bug report, leave an issue on the issues page or send a pull request. For general questions and comments, use the http://www.jqwidgets.com/community/forum/asp-net-mvc/ forum.
