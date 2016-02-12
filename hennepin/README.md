#Hennepin County bike and related data

### Main arcgis open data site[link](http://gis.hennepin.opendata.arcgis.com/)


##GIS Datasets of interest

####Hennepin County Bikeway System [link](http://gis.hennepin.opendata.arcgis.com/datasets/938c8598f0a0439a8d612bb7894a05cc_1)
- from the description `does not represent all on- and off-street bikeways in Hennepin County`
- as defined by the 2040 Bicycle Transportation Plan
- metadata [link to pdf](https://gis.hennepin.us/OpenData/Metadata/Bikeways.pdf) **5 attributes including geometry**
- EPSG:26915
- 5256 records

#####Differences with cyclopath data `select count(h.gid) from hcbikeways h JOIN hccyclopath c on ST_EQUALS(c.geom, h.geom);`
- none of the cyclopath data and hennepin county data are spatially equal (ST_EQUALS)
- 1044 of the hennepin county data are not within 3 meters (ST_DWITHIN) of a cyclopath trail (Cyclopath contains on- and off-street trails, and regular roads
- 1044 includes hennepin county data that is outside of hennepin county
- 679 differ by 3 meters within hennepin county

#####Differences with MetCouncil data [link](https://gisdata.mn.gov/dataset/us-mn-state-metc-trans-bikeways)
- Generally ~40% differ by more than 3 meters with MetCouncil Data
- 2528 hennepin county on/off-street trails aren't within 3 meters of a MetCouncil trail



#####Differences with the Hennepin portion of the Minnesota roads [link](https://gisdata.mn.gov/dataset/trans-roads-mndot-tis) provided by MNDOT
-- 77 on-street trails are 3 meters away from a road