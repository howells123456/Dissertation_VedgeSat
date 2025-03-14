# Code explination and disclaimer  


This Code was used for my dissertation and was adapted from - https://github.com/fmemuir/COASTGUARD
The changes to this code are shown below, refrencing what was changed to Muir code, the code used was updated on the 3rd of March 2025 thus Muir code may have changed since this update.  

e.g #Define name of site - line 29 
sitename = 'Test'  

Line 29 is the code in Muir code and the name was changed to 'Test' on this code

# Changes made below 
## VedgeSat_DriverTemplate.ipyn  

VedgeSat_Driver_Exapmle was merged when loaded onto juptyre notebook under the name TestGower with the following lines edited/taken outwith the line refrencing Muir code 


#Define name of site,  line 29 changed from SITENAME
sitename = 'Test'  

#Date range, line 32 changed from dates = ['2021-05-01', '2021-07-02']
dates = ['2014-01-01', '2024-12-12']  


#Satellite missions, line 35 changed to all of the satellites 
#Input a list of containing any/all of 'L5', 'L7', 'L8', 'L9', 'S2', 'PSScene4Band'
#L5: 1984-2013; L7: 1999-2017 (SLC error from 2003); L8: 2013-present; S2: 2014-present; L9: 2021-present
sat_list = ['L7, L8, L9, S2']  


#Reference shoreline/veg line shapefile name (should be stored in a folder called referenceLines in Data), line 46
referenceLineShp = 'Three Cliffs Bay.shp'  , my shp shorline name 


line 121 - 129 not added


'20180507T110621_20180507T110835_T31UDU_RGB_georef.tif',  line 142 removed  
 

 #Option 2 on line 157 used, 147 - 152 not used, use this if outputs need to be loaded   
 

 print finished # added under line 177 to test to see what was saving 

NoSmooths = 100 # changed to = 0 pn line 182 of muir code 
TransectSpacing = 10,  changed t0 400 to aim and get transects 400 meters apart did not work 
DistanceInland = 100, changed to 200 for better placement of transects
DistanceOffshore = 100

WaterlineShp = glob.glob(LinesPath+'/*waterlines.shp'),  line 197 and 198 commented out as vegetation lines were main focus 
WaterlineGDF = gpd.read_file(WaterlineShp[0])


shp_path = os.path.join(filepath, sitename, 'intersections', sitename + '_transect_intersects.shp'), line added after 215 of Muir code 


.WavesIntersect(settings, TransectInterGDF, BasePath, output, lonmin, lonmax, latmin, latmax), line 239 added due to an update in VegdeSat

Line 233 - 302 of Muir code removed as not focusing on waterlines

lines 314 - 320 of Muir code removed 

DatesCol = 'Date', line 327 changed to dates to match atribute table in QGis

line 328 changed to ValidationShp = ValidationShp = 'C:\\Users\\charl\\Downloads\\Repro3cliffs.shp' - to match my files

print(ValidInterGDF), added under line 341 to test if the above was loading in Muir code

line 346, changed to TransectIDList = [(0,59),(60,119),(120,179),(180,240)]

 
## Changes to transects 

line 1799 of Muir code , Just in case they aren't the same, reproject validation lines to match transect CRS

                         ValidGDF.to_crs(TransectGDF.crs, inplace=True)

    

