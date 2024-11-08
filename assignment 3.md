Project `Fieldtrip_locations`
geojson URL: - ADD

Processing hsitroy 
```python
processing.run("native:reprojectlayer", {'INPUT':'C:/Users/localuser/Documents/GIS data/fielwork_locations.geojson','TARGET_CRS':QgsCoordinateReferenceSystem('EPSG:25830'),'CONVERT_CURVED_GEOMETRIES':False,'OPERATION':'+proj=pipeline +step +proj=unitconvert +xy_in=deg +xy_out=rad +step +proj=utm +zone=30 +ellps=GRS80','OUTPUT':'ogr:dbname=\'C:/Users/localuser/Documents/GIS data/fieldwork_location_25830.gpkg\' table="fieldwork locations" (geom)'})
```

create buffer 
```python
 processing.run("native:buffer", {'INPUT':'C:/Users/localuser/Documents/GIS data/fieldwork_location_25830.gpkg|layername=fieldwork locations','DISTANCE':3000,'SEGMENTS':8,'END_CAP_STYLE':0,'JOIN_STYLE':0,'MITER_LIMIT':2,'DISSOLVE':False,'SEPARATE_DISJOINT':False,'OUTPUT':'TEMPORARY_OUTPUT'})
```

Added tif file:
URL: `https://livingatlas.arcgis.com/landcoverexplorer/#mapCenter=-3.28600%2C31.34000%2C3&mode=step&timeExtent=2017%2C2021&year=2022&downloadMode=true`
tif file: 
