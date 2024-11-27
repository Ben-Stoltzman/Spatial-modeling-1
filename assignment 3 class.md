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

Added zonal histogram
```python
processing.run("native:zonalhistogram", {'INPUT_RASTER':'C:/Users/localuser/Documents/GIS data/30T_20230101-20240101.tif','RASTER_BAND':1,'INPUT_VECTOR':'C:\\Users\\localuser\\Documents\\GIS data\\3km_buffer_fieldwork_locations.gpkg|layername=buffered','COLUMN_PREFIX':'LC_','OUTPUT':'ogr:dbname=\'C:/Users/localuser/Documents/GIS data/3km_buffer_fieldwork_locations_LC_HIST.gpkg\' table="LC_HIST" (geom)'})
```

Displayed data datawrapper: `https://app.datawrapper.de/chart/LXtNd/visualize#refine`
