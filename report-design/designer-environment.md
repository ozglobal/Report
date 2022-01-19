# Components

## ReportTemplate

The **root object** containing all other components such as reports, bands, labels, etc.

* Home > Preview
  * Preview  language:
  * Preview type: HTML5
* Properties
  * Grid
  * Snap To Grid
  * MeasurementUnits

## Report

* A space corresponding to a page on which to put various bands
* The ReportTemplate contains a single Report by default.&#x20;
* Paper Type: A4&#x20;

## Band

OZ Report Designer uses a "band-oriented" design approach. A Report Band represents a specific area on a report page, used to specify where and when, and how the report components are to be displayed on the report. All components in the report (label, table, crosstab, chart, shape, input component, etc.) are located in one of several bands.‌

#### Types of Bands <a href="#types-of-bands" id="types-of-bands"></a>

| Band         | Description                                      |
| ------------ | ------------------------------------------------ |
| Page Header  | prints at the top of every page.                 |
| Title        | prints at the start of the report                |
| Data Header  | prints at the start of the associated data band. |
| Data         | prints dataset on repeated pages                 |
| Group Header | prints at the start of a group                   |
| Group Footer | prints at the end of a group                     |
| Data Footer  | prints at the end of the associated data band.   |
| Page Footer  | prints at the bottom of every page               |
| Summary      | prints summarized data of the entire report      |
| Dummy        | prints blank with no data                        |
| Tail         | prints at the end of the report                  |

#### Key properties of the Data band <a href="#key-properties-of-data-band" id="key-properties-of-data-band"></a>

| Property       | Description                              |
| -------------- | ---------------------------------------- |
| Master Name    | Mater band name of the current data band |
| ODI Name       | ODI Name for the data band               |
| Dataset Name   | Dataset Name for the data band           |
| Fix Master     | Prints Master band on every page         |
| Fix Title      | Prints Data Header band on every page    |
| Force New Page | Insert page break                        |
| Repeat Number  | Repeat count of records                  |

## Label

| Type     | Description                                                             |
| -------- | ----------------------------------------------------------------------- |
| Text     | prints text                                                             |
| Data     | prints the value of a dataset field                                     |
| Summary  | prints aggregation of values of a field (Sum, Avg, Max, Min, Cnt, None) |
| Group    | prints field values grouped by the same values                          |
| System   | prints values provided by the viewer (date, page number, etc.)          |
| Barcode  | prints a value as a barcode image                                       |
| Image    | prints an image                                                         |
| HTML     | prints HTML                                                             |
| Resource | for multi-lingual report                                                |

## Multiplex component

| Component  | Description                                              |
| ---------- | -------------------------------------------------------- |
| FixedTable | a table of label cells                                   |
| Table      | prints all result rows from a dataset                    |
| Crosstab   | generates a pivot table from a dataset                   |
| Chart      | draws a chart from a dataset (bar, pie, line, dot, etc.) |
