# Componentes

## ReportTemplate

El objeto base \(**root object\)** que contiene al resto de componentes como reports, bands, labels, etc.

* Home &gt; Preview
  * Preview  language:
  * Preview type: HTML5
* Properties
  * Grid
  * Snap To Grid
  * MeasurementUnits

## Report

* Espacio \(que corresponde a una página o documento\) donde colocar las bandas
* De inicio, el ReportTemplate contiene un solo Report pero el usuario puede crear mas reports dentro del mismo ReportTemplate
* Paper Type: A4 

## Band

El diseño de reportes realizado en OZ Report Designer está basado en un sistema de bandas, que definen regiones de trabajo donde colocar los componentes. Una banda representa un área específica del reporte usada para definir cuándo, dónde, y cómo se mostrarán los componentes en el reporte. Todos los componentes del reporte \(label, table, crosstab, chart, shape, input component, etc.\) han de estar contenidos en alguno de los diversos tipos de bandas.‌

#### Tipos de Bandas <a id="types-of-bands"></a>

| Banda | Descripción |
| :--- | :--- |
| Page Header | Se muestra al inicio de cada página |
| Title | Se muestra al inicio del reporte |
| Data Header | Se muestra al inicio de la banda de datos asociada |
| Data | Muestra los datos del dataset en tantas páginas como sea necesario |
| Group Header | Se muestra al inicio de un grupo |
| Group Footer | Se muestra al final de un grupo |
| Data Footer | Se muestra al final de la banda de datos asociada |
| Page Footer | Se muestro al final de cada página |
| Summary | Muestra información resumen de todo el reporte |
| Dummy | Muestra espacio en blanco en el lugar donde se coloca. No sirve para mostrar datos. Se utiliza para componentes meramente visuales que no necesitan acceso al archivo ODI |
| Tail | Se muestra al final del reporte |

#### Propiedades Principales de las Bandas de Datos \(Data Bands\) <a id="key-properties-of-data-band"></a>

| Propiedad | Descripción |
| :--- | :--- |
| Master Name | Nombre de la banda Master de la banda de datos seleccionada |
| ODI Name | Nombre del ODI usado por la banda de datos |
| Dataset Name | Nombre del dataset usado por la banda de datos |
| Fix Master | Muestra la banda Master correspondiente en cada página |
| Fix Title | Muestra la banda Master Header correspondiente en cada página |
| Force New Page | Inserta un salto de página |
| Repeat Number | Número de veces a mostrar la banda de datos |

## Label

| Tipo | Descripción |
| :--- | :--- |
| Text | Imprime texto |
| Data | Imprime el valor de una columna \(campo\) del dataset |
| Summary | Imprime el resultado de distintas funciones aplicadas a los campos de los datos \(Sum, Avg, Max, Min, Cnt, None\) |
| Group | Imprime valores de los campos del dataset, agrupados para que no se repitan |
| System | Imprime valores proveidos por el visualizador \(date, page number, etc.\) |
| Barcode | Imprime un valor en forma de código de barras |
| Image | Imprime una imagen |
| HTML | Imrpime texto formateado en HTML |
| Resource | Para reportes en varios idiomas |

## Componentes Multiplex 

| Componente | Descripción |
| :--- | :--- |
| FixedTable | Una tabla con celdas tipo Label |
| Table | Muestra todos los resultados de las columnas seleccionadas del dataset |
| Crosstab | Genera una tabla pivote a partir del dataset |
| Chart | Genera gráficas a partir del dataset  \(bar, pie, line, dot, etc.\) |

