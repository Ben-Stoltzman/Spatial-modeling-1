# Exclusion of solar panel areas in Segovia 
1. Exporting the selected feature of segovia as geopackage
2. clipping solar exclusion with segobvia province
   ```python
   processing.run("native:clip",
   {'INPUT':'C:/Users/localuser/Documents/GIS data/enre_cyl_excl_foto.gpkg|layername=enre_cyl_excl_foto',
   'OVERLAY':'C:/Users/localuser/Documents/GIS data/segovia_province.gpkg|layername=prov_cyl_recintos',
   'OUTPUT':'TEMPORARY_OUTPUT'})
   ```
3. Dissolve the solar exclusion in segovia
   ```python
    processing.run("native:dissolve", {'INPUT':'C:\\Users\\localuser\\Documents\\GIS data\\solar_exclusion_segovia.gpkg|layername=solar exclusion segovia','FIELD':[],'SEPARATE_DISJOINT':False,'OUTPUT':'TEMPORARY_OUTPUT'})
   ```
   => manually made permanenet with the name: `solar_exclusion_Segovia_dissolved.gpkg`
