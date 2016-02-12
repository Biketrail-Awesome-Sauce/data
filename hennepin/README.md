#Hennepin County bike and related data

### Main arcgis open data site[link](http://gis.hennepin.opendata.arcgis.com/)


##GIS Datasets of interest

####Hennepin County Bikeway System [link](http://gis.hennepin.opendata.arcgis.com/datasets/938c8598f0a0439a8d612bb7894a05cc_1)
- from the description `does not represent all on- and off-street bikeways in Hennepin County`
- as defined by the 2040 Bicycle Transportation Plan
- metadata [link to pdf](https://gis.hennepin.us/OpenData/Metadata/Bikeways.pdf) **5 attributes including geometry**
- EPSG:26915
- 5256 records

#####Differences with cyclopath data `select count(h.gid) from hcbikeways h LEFT JOIN hccyclopath c on ST_EQUALS(c.geom, h.geom) where c.gid is NULL;`
     - none of the cyclopath data and hennepin county data are spatially equal (ST_EQUALS)
     - 1044 of the hennepin county data are not within 3 meters (ST_DWITHIN) of a cyclopath trail (Cyclopath contains on and off trails, and regular roads
     - 1044 includes hennepin county data that is outside of hennepin county
     - 679 differ by 3 meters within hennepin county