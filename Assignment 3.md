The first layers that I added were:
1. Cattle roads `https://idecyl.jcyl.es/geonetwork/srv/spa/catalog.search#/metadata/SPAGOBCYLMNADTSAMVPE`
2. _Microtus Arvalis_ Distribution `https://www.gbif.org/occurrence/map?taxon_key=2438606&gadm_gid=ESP.5_1`
3. Medium Resolution Net Primary Production `https://sdi.eea.europa.eu/catalogue/srv/eng/catalog.search#/metadata/47e902f8-8237-415b-91fc-6d1522b11417`

Then I clipped the Medium Resolution Net Primary Production to the Segovia province 
```python
processing.run("gdal:cliprasterbymasklayer", {'INPUT':'/vsizip/C:/Users/localuser/Downloads/eea_r_3035_196_m_modis-npp_p_2000-2022_v01_r00.zip/eea_r_3035_196_m_modis-npp_p_2000-2022_v01_r00/all_tilessmoothed_2000_3035.tif','MASK':'C:/Users/localuser/Documents/GIS data/sg_province.gpkg|layername=prov_cyl_recintos','SOURCE_CRS':None,'TARGET_CRS':None,'TARGET_EXTENT':None,'NODATA':None,'ALPHA_BAND':False,'CROP_TO_CUTLINE':True,'KEEP_RESOLUTION':False,'SET_RESOLUTION':False,'X_RESOLUTION':None,'Y_RESOLUTION':None,'MULTITHREADING':False,'OPTIONS':'','DATA_TYPE':0,'EXTRA':'','OUTPUT':'TEMPORARY_OUTPUT'})
```

The importance of this was to determine the Productivity of farmlands where Cattle roads cross over and too see which specific area within the province we believe is suitable to start our project. 