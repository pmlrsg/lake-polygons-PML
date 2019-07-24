# lake-polygons-PML
![doi badge](https://zenodo.org/badge/69982025.svg)

This repository contains well-known-text (WKT) representations of the maximum water extent of a large number of water bodies. They have been created in the following steps:

1: raster data source: ESACCI-LC-L4-WB-Map-150m0P13Y-2000-v4.0, see http://www.esa-landcover-cci.org/

2: conversion of geotiff to shapefiles in 10x10 degree tiles using GDAL polygonize

3: manual matching of lake locations to polygons using the Global Lake and Wetlands Database (GLWD) for reference, editing (combining, splicing) polygons as necessary.

Each polygon has an identifier consisting of a dataset identifier (4 characters) and a sequential number (8 digits).
The dataset identifier may be replaced by a single digit, where the provenance of the polygon definition is as follows:

- 0: GLWD, referring to polygon definitions corresponding to the Global Lake and Wetlands Database 
- 1: GLBL, referring to polygons defined in the UK GloboLakes project
- 2: CGL2, referring to polygons defined for the Copernicus land monitoring service - water quality 
- 3: HYLA, referring to polygons definitions corresponding to  Hydrolakes v10 (https://www.hydrosheds.org/page/hydrolakes)

To avoid any doubt, polygons indicated as GLWD or HYLA are not identical to the polygons offered in the respective datasets. They are still traced from the maximum water extent observed in the ESA landcover CCI, but should correspond closely in spatial definition and naming conventions to either GLWD or HYLA.

Polygons describing the same water body as those occurring in the GLWD or HYLA adopt the respective index nr as their identifier, except if they have been significantly altered, for example by splitting up or combining connected water bodies, in which case the identifier belongs to a specific project (GLBL, CGL2). 

The dataset includes Polygons as well as Multipolygons. Islands are not excluded as a rule although in some polygons these are defined as holes. This is due to inconsistent behaviour of the polygonizing step in GDAL. In the 2019 ('4k') version of the data, all polygons have been validated using python-shapely.

The polygons are provided in three sets:
- globolakes: The GloboLakes 1000 lakes as used with Calimnos up to v1.04
- cglops: The Copernicus Land Monitoring Service set as used with Calimnos up to v1.2, inluding > 1000 water bodies including those adopted from GMES Africa
- CLMS4k: The Copernicus Land Monitoring Service set as used with Calimnos from v1.3, including over 4000 water bodies, produced in collaboration with Brockmann Consult.

There is substantial overlap between these sets. The currently recommended set is CLMS4k. 

Please direct any enquiries to calimnos-support@pml.ac.uk

