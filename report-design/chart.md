---
description: Design a bar and pie chart
---

# Chart

## Target Report

[Example](http://oz.ozeform.io/oz/edu/reportdev/order-chart.html)

## order-chart.ozr

1. Create a new ReportTemplate and save it as **`order-chart.ozr`**.
2. **Insert ODI\(D\)** -&gt; **order.odi**
3. Add a Data band
4. Add **Chart** to the Data band

### Horizontal bar

1. Chart Type &gt; Horizontal bar
2. Data
   1. X-Axis &gt; Country
   2. Y-Axis Left &gt; TotalDue \(sum\)
   3. Apply
3. Title
   1. Chart Title "Total Due By Country \(Bar Chart\)"
4. X-Axis
   1. Show Major Gridline &gt; uncheck
   2. Show Label &gt; Format &gt; Paragraph &gt; Alignment &gt; Horizontal &gt; Right justified
   3. Apply
5. Y-Axis
   1. Show Major Gridline &gt; Line Style &gt; Use dashed line &gt; Length 1, Gap 2
   2. Show label\(Left\) &gt; Format &gt; UNIT &gt; Type 12.3K
   3. Apply
6. Data Label
   1. Data Label &gt; Show &gt; Format &gt; Currency
   2. Apply
7. Misc
   1. Bar Thick &gt; 0.5
   2. Apply
8. Display
   1. BackGround &gt; Fill &gt; select color
   2. Apply
9. OK

### Pie chart

1. Chart Type &gt; Pie
2. Data
   1. X-Axis &gt; Country
   2. Y-Axis Left &gt; TotalDue \(sum\)
   3. Apply
3. Title
   1. Chart Title "Total Due By Country \(Pie Chart\)"
4. Data Label
   1. Data Label &gt; Show &gt; Format &gt; Currency
   2. Data to Show &gt; Item name, Value
   3. Apply
5. Pie
   1. Axis Thickness &gt; 60
   2. Data label Position &gt; Side Pos
6. Legend
   1. Uncheck Show
   2. Apply
7. OK



