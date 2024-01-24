---
layout: page
title: Unidad 2 - Obtención de datos matriciales (ráster)
parent: Módulo 1 - Obtención de datos y Operaciones Análiticas en la Práctica
nav_order: 2
---

# Obtención de datos matriciales (ráster)
Los datos matriciales, también conocidos como datos ráster, son uno de los dos tipos principales de datos geoespaciales, siendo el otro los datos vectoriales.

Los datos ráster son una forma de representar información geoespacial en un formato de cuadrícula. Cada celda en la cuadrícula representa un área específica en la superficie de la Tierra y contiene un valor que representa alguna característica de ese área. Los datos ráster son especialmente útiles para representar fenómenos continuos, como la elevación del terreno, la temperatura, la precipitación, etc.

#### Características
1. Estructura de cuadrícula: Los datos ráster se organizan en una estructura de cuadrícula donde cada celda o píxel contiene un valor.
2. Representación de datos continuos: Los datos ráster son ideales para representar datos continuos como la elevación del terreno, la temperatura, etc.
3. Resolución: La resolución de los datos ráster se refiere al tamaño de cada celda en la cuadrícula. Una resolución más alta significa que cada celda representa una menor área en la superficie de la Tierra, lo que resulta en un mayor nivel de detalle.
4. Valores de celda: Cada celda en un ráster puede contener un valor que representa alguna característica de esa área en la superficie de la Tierra.

## Interés para el control público
La importancia de los datos ráster en los Sistemas de Información Geográfica (GIS) radica en su capacidad para representar datos geoespaciales de manera detallada y precisa. Los datos ráster permiten a los usuarios visualizar y analizar patrones geoespaciales y relaciones en los datos. Esto es especialmente útil en aplicaciones como la modelización del terreno, el análisis de la cobertura del suelo, la modelización del clima, entre otros. 

The ASF DAAC is not limited to data from NASA-led satellite missions. It contains data from a wide range of satellites, including but not limited to: Sentinel-1, RADARSAT-1, European Remote Sensing Satellite-1 and -2 (ERS-1 and -2), ALOS PALSAR, Japanese Earth Resource Satellite-1 (JERS-1), SMAP, and Seasat, in addition to the airborne sensors AirSAR and UAVSAR.

#### Exercise 1.2 Access SAR data using the ASF DAAC.
1. Navigate the ASF Data Portal: [http://vertex.daac.asf.alaska.edu/](http://vertex.daac.asf.alaska.edu/)
2. In the upper search panel, set the `Search Type` to `Geographic Search` and the `Dataset` to `Sentinel-1`. 
3. Click on the `Filters` button.
    1. Under the `Area of Interest` field, input  `POLYGON((-50.985 -0.8565,-50.0179 -0.8565,-50.0179 0.0347,-50.985 0.0347,-50.985 -0.8565))`. Note that as an alternative, you could upload a shapefile for the specific area you are interested in, or draw an area of interest on the map directly.
    2. Under the `Date Filters` field, input `1/1/2023` as the `Start Date` and `1/25/2023` as the `End Date`. 
4. Click `Search`.
5. Select the first image result. Note that this is the same image as the one we found with the Earthdata search (you can check the granule IS). Feel free to explore the other images the search returned by scrolling through the results.
6. In the right-hand `Scene Detail` panel, you can read about the metadata of the image, view the image in the image viewer, or download the image. Click on the icon that looks like an eye to `Open in Image Viewer`. 
7. *Do not complete this step. It is the same file you downloaded in the previous exercise.* Click on the `L1 Detected High-Res Dual-Pol (GRD-HD)` product. Download the image product file.

## Sentinel-1 File Naming
The file names of Sentinel-1 data products follow a specific naming convention that provides information about the product and the acquisition conditions. The format of the Sentinel-1 file names is as follows:

`S1[A/B]_[IW/EW]_[TTTR]_[YYYYMMDD]T[HHMMSS]_[YYYYMMDD]T[HHMMSS]_[OOOOOO]_[DDDDDD]_[CCC].zip`

* `S1[A/B]`: Indicates the Sentinel-1 satellite, where A stands for Sentinel-1A and B for Sentinel-1B.
* `[IW/EW]`: Indicates the product type, where `IW` stands for Interferometric Wide swath and `EW` for Extra-Wide swath.
* `[TTTR]`: Indicates the product type and resolution. The product types can be `RAW`, `SLC`, `GRD`, or `OCN`. The resolution `R` can be `F` (full), `H` (high), or `M` (medium).
* `[LFPP]`: Indicates the processing level L, the product class F, and the polarization PP. L can be `1` or `2`, F can be `S` (standard) or `A` (annotation), and PP can be `SH` (single HH), `SV` (single VV), `DH` (dual HH + HV), or `DV` (dual VV + VH).
* `[YYYYMMDD]T[HHMMSS]`: Indicates the start and stop date and time of the acquisition (respectively), where `YYYY` is the year, `MM` is the month, `DD` is the day, and `HHMMSS` is the hour, minute, and second.
* `[OOOOOO]`: Indicates the absolute orbit number of the product.
* `[DDDDDD]`: Indicates the mission data-take identifier.
* `[CCCC]`: Indicates the product unique identifier.

Example: `S1A_IW_GRDH_1SSH_20201231T155959_20201231T160004_031117_03F1E1.zip`

This file name corresponds to a Level 1 Standard Sentinel-1A product acquired on December 31st, 2020, 15:59:59 UTC, with the Interferometric Wide swath mode, the Ground Range Detected High resolution mode, and with single HH polarization.

It's worth noting that the format of the file name may change depending on the specific mission or the data provider. It is recommended to consult with the data provider or refer to the documentation provided to get a better understanding of the file naming conventions.
