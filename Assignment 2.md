# Areas in Segovia where livestock roads are located #
1. Exporting the selected feature of segovia as geopackage
2. clipping livestock roads segovia province
   ```python
  processing.run("native:clip", {'INPUT':'/Users/benstoltzman/Downloads/znie_cyl_vvpp_ejes/znie_cyl_vvpp_ejes.shp','OVERLAY':'/Users/benstoltzman/Desktop/QGIS/Assignment 2/sg_province.gpkg|layername=prov_cyl_recintos','OUTPUT':'TEMPORARY_OUTPUT'})

  manually exported with the file name: ''sg_livestock.gpkg''
   ```
3. Dissolve the livestock roads in segovia
   ```python
   processing.run("native:dissolve", {'INPUT':'/Users/benstoltzman/Desktop/QGIS/Assignment 2/sg_livestock.gpkg|layername=segovia_livestock','FIELD':[],'SEPARATE_DISJOINT':False,'OUTPUT':'ogr:dbname=\'/Users/benstoltzman/Desktop/QGIS/Assignment 2/sg_livestock.gpkg\' table="segovia_livestock_ds" (geom)'})
   ```
   => manually made permanenet with the name: ``segovia_livestock.ds''
