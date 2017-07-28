# lake-polygons-PML

This repository contains well-known-text (WKT) representations of the maximum water extent of a large number of water bodies. They have been created in the following steps:

1: raster data source: ESACCI-LC-L4-WB-Map-150m0P13Y-2000-v4.0, see http://www.esa-landcover-cci.org/

2: conversion of geotiff to shapefiles in 10x10 degree tiles using GDAL polygonize

3: manual matching of lake locations to polygons using the Global Lake and Wetlands Database (GLWD) for reference, editing (combining, splicing) polygons as necessary.

Each polygon is characterized by an identifier consisting of a dataset identifier (4 characters) and a sequential number (8 digits). 

At present three datasets are included: 
- GLWD, referring to the Global Lake and Wetlands Database 
- GLBL, referring to the UK GloboLakes project
- CGL2, referring to the Copernicus land service - Water quality products

Polygons describing the same water body as those occurring in the GLWD will always adopted the GLWD index as their identifier, except if they have been significantly altered, for example by splitting up or combining connected water bodies. 

The dataset includes Polygons as well as Multipolygons. Islands are not excluded as a rule although in some polygons these are defined as holes. This is due to inconsistent behaviour of the polygonizing step in GDAL.

The polygons are provided in two sets, one pertaining to the GloboLakes 1000 lakes and one for the Copernicus Land Service. There is substantial overlap between these. To obtain all polygons simply merge the contents of the two folders overwriting those with identical names. 


Please direct any enquiries to calimnos-support@pml.ac.uk

