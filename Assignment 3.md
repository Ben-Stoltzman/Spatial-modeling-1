# Monterrubio Site 

The first layers that I added were:
1. Livestock corridors `https://idecyl.jcyl.es/geonetwork/srv/spa/catalog.search#/metadata/SPAGOBCYLMNADTSAMVPE`
2. _Microtus Arvalis_ Distribution `https://www.gbif.org/occurrence/map?taxon_key=2438606&gadm_gid=ESP.5_1`
3. Medium Resolution Net Primary Production `https://sdi.eea.europa.eu/catalogue/srv/eng/catalog.search#/metadata/47e902f8-8237-415b-91fc-6d1522b11417`

Then I clipped the Medium Resolution Net Primary Production to the Segovia province 
```python
processing.run("gdal:cliprasterbymasklayer", {'INPUT':'/vsizip/C:/Users/localuser/Downloads/eea_r_3035_196_m_modis-npp_p_2000-2022_v01_r00.zip/eea_r_3035_196_m_modis-npp_p_2000-2022_v01_r00/all_tilessmoothed_2000_3035.tif','MASK':'C:/Users/localuser/Documents/GIS data/sg_province.gpkg|layername=prov_cyl_recintos','SOURCE_CRS':None,'TARGET_CRS':None,'TARGET_EXTENT':None,'NODATA':None,'ALPHA_BAND':False,'CROP_TO_CUTLINE':True,'KEEP_RESOLUTION':False,'SET_RESOLUTION':False,'X_RESOLUTION':None,'Y_RESOLUTION':None,'MULTITHREADING':False,'OPTIONS':'','DATA_TYPE':0,'EXTRA':'','OUTPUT':'TEMPORARY_OUTPUT'})
```

The importance of this was to determine the Productivity of farmlands where Cattle roads cross over and to see which specific area within the province we believe is suitable to start our project. 

We identified a region in Monterrubio, with Coordinates: `40°49'06.5"N 4°21'21.9"W` where the cattle road eventually intersects through a Red Natura 2000 ZEPA zone, which I downloaded from `https://idecyl.jcyl.es/geonetwork/srv/spa/catalog.search#/metadata/SPAGOBCYLMNADTSPSZEC`.
This is important since in order for predators to return to our rewilded sites, there needs to be already established populations nearby. I identified that the productivity was lower within croplands whcih were on the left of the cattle road and this is where we believe our project could be piloted. This location was characterised by farmlands nearby a river and surrounded by some natural vegetation with a large enough area to support predators to eventually move into our rewilded corridors. 

The next file I added was the Farmland field margins in order to understand the primary productivity of these borders and then added a 3m buffer around these borders, where rewilding will take place.
```python
processing.run("native:buffer", {'INPUT':'farm_borders_M.gpkg|layername=farm_borders','DISTANCE':3,'SEGMENTS':5,'END_CAP_STYLE':0,'JOIN_STYLE':0,'MITER_LIMIT':2,'DISSOLVE':False,'SEPARATE_DISJOINT':False,'OUTPUT':'TEMPORARY_OUTPUT'})
```
The importance of this map was to show the high primary productivity (indicated by dark green) in g C/m²/year. With the high primary productivity within the Red Natura 2000 site being close to our piloted site it would most likely ensure a higher probability of species moving to the rewilded site. Higher primary productivity would show more stable ecosystems. 

[Map 1 Assignment 3.pdf](https://github.com/user-attachments/files/17969888/Map.1.Assignment.3.pdf)



# 2km buffer around Monterrubio site 

The first layer I added was the Land cover map of Spain from ESRI downloaded from: `https://livingatlas.arcgis.com/landcoverexplorer/#mapCenter=55.24574%2C25.06542%2C11&mode=step&timeExtent=2017%2C2023&year=2023&downloadMode=true`
I then clipped the file to be within the Segovia province as the focus will be on the Monterrubio site. 
I then had to copy the orignal style from the map and apply it to the clipped version so show the same symbology.

I then added the same livestock corridor data, clipped it to Segovia province and created 2km buffers around these lkivesock corridors. This 2km was suggested as the correct size for animal species, especially bird species in surrounding protected areas to be able to move into these rewilded livestock corridors. 
```python
processing.run("native:buffer", {'INPUT':'Livestock_roads_Segovia.gpkg|layername=livestock_roads_segovia','DISTANCE':2000,'SEGMENTS':5,'END_CAP_STYLE':0,'JOIN_STYLE':0,'MITER_LIMIT':2,'DISSOLVE':False,'SEPARATE_DISJOINT':False,'OUTPUT':'TEMPORARY_OUTPUT'})
```
I then changed the symbology of the buffers to have a low opacity so to clearly see the distance that the buffers on the cattle roads interact with the surrounding environments. 
The importance of this map was to understand the surrounding ecosystems and land use to determine whether this site ould be suitable to start rewilding. 

[Map 2.pdf](https://github.com/user-attachments/files/17969977/Map.2.pdf)


Questions:
1. I really would like to know how I could clip a certain part or distance of the cattle road to be able to do my geoprocessing with, for example 10km of the cattle road that passes through Monterrubio and not all the cattle roads.
   
2. I would also like to be able to clip the landcover map to display only within the 2km buffers, as I wanted to work out the percent of the the different landcovers that the buffer contains to assess the probability that species would use these rewilded sites based on the amount of native vegatation already present. I remember we did something similar in class and we displayed the information on excel. 






