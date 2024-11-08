Project `Fieldtrip_locations`
geojson URL: - ADD

Processing hsitroy 
```python
processing.run("native:reprojectlayer", {'INPUT':'C:/Users/localuser/Documents/GIS data/fielwork_locations.geojson','TARGET_CRS':QgsCoordinateReferenceSystem('EPSG:25830'),'CONVERT_CURVED_GEOMETRIES':False,'OPERATION':'+proj=pipeline +step +proj=unitconvert +xy_in=deg +xy_out=rad +step +proj=utm +zone=30 +ellps=GRS80','OUTPUT':'ogr:dbname=\'C:/Users/localuser/Documents/GIS data/fieldwork_location_25830.gpkg\' table="fieldwork locations" (geom)'})
```
