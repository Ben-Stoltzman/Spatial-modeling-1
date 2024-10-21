# Areas in Segovia where livestock roads are located #
1. Exporting the selected feature of segovia as geopackage
   
2. clipping livestock roads segovia province
```python
  processing.run("native:clip", {'INPUT':'/Users/benstoltzman/Downloads/znie_cyl_vvpp_ejes/znie_cyl_vvpp_ejes.shp','OVERLAY':'/Users/benstoltzman/Desktop/QGIS/Assignment 2/sg_province.gpkg|layername=prov_cyl_recintos','OUTPUT':'TEMPORARY_OUTPUT'})
```
  

3. Dissolve the livestock roads in segovia
   ```python
   processing.run("native:dissolve", {'INPUT':'/Users/benstoltzman/Desktop/QGIS/Assignment 2/sg_livestock.gpkg|layername=segovia_livestock','FIELD':[],'SEPARATE_DISJOINT':False,'OUTPUT':'ogr:dbname=\'/Users/benstoltzman/Desktop/QGIS/Assignment 2/sg_livestock.gpkg\' table="segovia_livestock_ds" (geom)'})


4. Downloaded WMS file of cultivated land in Castilla y Leon
   link for download: `https://mcsncyl.itacyl.es/arcgis/services/MCSNCyL/MapServer/WMSServer?`
   I was unable to clip the layeer to just the Segovia region, multiple errors kept appearing

5. Downloaded WMS file called: Woody landscape features on agricultural land
Link to webpage: `https://sdi.eea.europa.eu/catalogue/srv/eng/catalog.search#/metadata/c8187fa6-fada-43a3-b017-e567e045525d`
Link to download WMS: `https://land.discomap.eea.europa.eu/arcgis/services/Agriculture/Woody_landscape_features_on_agricultural_land_2018/MapServer/WMSServer?request=GetCapabilities&service=WMS`
Citation: (2024). Woody landscape features on agricultural land. 
https://sdi.eea.europa.eu/catalogue/srv/api/records/c8187fa6-fada-43a3-b017-e567e045525d 
File was also unable to be clipped to Segovia. 


6. Downloaded WMS filed called: Tree Cover Change Mask 2015-2018 (raster 20 m), Europe, 3-yearly, Dec. 2020
   Link to webpage: `https://sdi.eea.europa.eu/catalogue/srv/eng/catalog.search#/metadata/9723d33f-ac36-49d0-b2c7-80710d377a7d`
Link to download WMS: `https://image.discomap.eea.europa.eu/arcgis/services/GioLandPublic/HRL_TreeCoverChangeMask_15_18/ImageServer/WMSServer?request=GetCapabilities&service=WMS`
File was also unable to be clipped to Segovia, multiple errors showing up.


I tried many times to clip rastor to mask layer or extent and clip it within the boundary of Segovia province file, but it kept on giving me multiple errors.

The reason behind choosing these layers is that our solutions are revolved around rewilding cattle roads and involving a more nature based approach. I chose these layers, because we need to have an undertsanding of the physical environment we are working in and undestand how the changes in land use can have a direct impact on the projects we are trying to propose. 
