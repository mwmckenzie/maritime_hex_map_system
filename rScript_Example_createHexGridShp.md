# R Script Example
## Creating and Exporting Shifted Hex Map Shapefiles
## Grid: ISEA4H
### Parameters: 
 - Boundaries: minlat = 18, minlon = -150, maxlat = 82, maxlon = 40
 - Resolutions: R4-R7 (analysis), R9 (coastlines and other boundaries)
 - Shift:  +30 deg (lon), + 0 deg (lat)\
 
> Example Workflow: 
> Creates a hex grid at resolution choice
> clips to lat/lon bounding box
> saves non-shifted grid to shp
> imports and shifts shp by 30 deg longitude
> saves shifted grid as shp
> copy and update name of .proj in export folder

## Required (R Libraries):
 - maptools
 - rgdal

### Updated Methodology (Nov 2022)

## Resolution 4 (R4)

### dggs <- dgconstruct("ISEA",aperture = 4, topology = "HEXAGON", spacing = 500, resround = "nearest", metric = TRUE)

> grid <- dgrectgrid(dggs, minlat = 18, minlon = -150, maxlat = 82, maxlon = 40, savegrid = "E:/Projects/HexagonR/ShpR/HexMap_ISEA4H_Res4_Wide.shp")

> grids <- "E:/Projects/HexagonR/ShpR/HexMap_ISEA4H_Res4_Wide.shp"

> loadedGrid <- readOGR(grids)

> shiftedGrid <- elide(loadedGrid, shift=c(30, 0))

> writeOGR(shiftedGrid, "E:/Projects/HexagonR/ShpR/HexMap_ISEA4H_Res4_WideOffset.shp", "HexMap_ISEA4H_Res4_Wide", driver="ESRI Shapefile")

## Resolution 5 (R5)

### dggs <- dgconstruct("ISEA",aperture = 4, topology = "HEXAGON", spacing = 250, resround = "nearest", metric = TRUE)

> grid <- dgrectgrid(dggs, minlat = 18, minlon = -150, maxlat = 82, maxlon = 40, savegrid = "E:/Projects/HexagonR/ShpR/HexMap_ISEA4H_Res5_Wide.shp")

> grids <- "E:/Projects/HexagonR/ShpR/HexMap_ISEA4H_Res5_Wide.shp"

> loadedGrid <- readOGR(grids)

> shiftedGrid <- elide(loadedGrid, shift=c(30, 0))

> writeOGR(shiftedGrid, "E:/Projects/HexagonR/ShpR/HexMap_ISEA4H_Res5_WideOffset.shp", "HexMap_ISEA4H_Res5_Wide", driver="ESRI Shapefile")

## Resolution 6 (R6)

### dggs <- dgconstruct("ISEA",aperture = 4, topology = "HEXAGON", spacing = 125, resround = "nearest", metric = TRUE)

> grid <- dgrectgrid(dggs, minlat = 18, minlon = -150, maxlat = 82, maxlon = 40, savegrid = "E:/Projects/HexagonR/ShpR/HexMap_ISEA4H_Res6_Wide.shp")

> grids <- "E:/Projects/HexagonR/ShpR/HexMap_ISEA4H_Res6_Wide.shp"

> loadedGrid <- readOGR(grids)

> shiftedGrid <- elide(loadedGrid, shift=c(30, 0))

> writeOGR(shiftedGrid, "E:/Projects/HexagonR/ShpR/HexMap_ISEA4H_Res6_WideOffset.shp", "HexMap_ISEA4H_Res6_Wide", driver="ESRI Shapefile")


-------


# Archived

dggs <- dgconstruct("ISEA",aperture = 4, topology = "HEXAGON", spacing = 10, resround = "nearest", metric = TRUE)

grid <- dgrectgrid(dggs, minlat = 25, minlon = -80, maxlat = 80, maxlon = 50, savegrid = "D:/GeographicData/HexMap_ISEA4H_res9_aor.shp")

grids9 <- "D:/GeographicData/HexMap_ISEA4H_res9_aor.shp"

temp9 <- readOGR(grids9)

temp9a <- elide(temp9, shift=c(30, 0))

writeOGR(temp9a, "D:/GeographicData/HexMap_ISEA4H_res9_aor_shifted.shp", "HexMap_ISEA4H_res9_aor", driver="ESRI Shapefile")


#### Updated Coords:

dggs <- dgconstruct("ISEA",aperture = 4, topology = "HEXAGON", spacing = 40, resround = "nearest", metric = TRUE)

grid <- dgrectgrid(dggs, minlat = 25, minlon = -120, maxlat = 80, maxlon = 30, savegrid = "D:/GeographicData/HexMap_ISEA4H_res8_AtlEur.shp")

grids8 <- "D:/GeographicData/HexMap_ISEA4H_res8_AtlEur.shp"

temp8 <- readOGR(grids8)

> temp8a <- elide(temp8, shift=c(30, 0))

> writeOGR(temp8a, "D:/GeographicData/HexMap_ISEA4H_res8_AtlEur_Shft30Lon.shp", "HexMap_ISEA4H_res8_AtlEur", driver="ESRI Shapefile")


---------


