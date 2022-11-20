# R Script Example
## Creating and Exporting Shifted Hex Map Shapefiles
## Grid: ISEA4H
### Cell Spacing: 
> Shift:  +30 deg (lon), + 0 deg (lat)
> Example: Creates a hex grid at resolution '9'; clips to lat/lon bounding box (25, -80), (80, 50); saves non-shifted grid to shp, imports and shifts shp by 30 deg longitude; saves shifted grid as shp

Required:
 - maptools
 - rgdal


dggs <- dgconstruct("ISEA",aperture = 4, topology = "HEXAGON", spacing = 10, resround = "nearest", metric = TRUE)

grid <- dgrectgrid(dggs, minlat = 25, minlon = -80, maxlat = 80, maxlon = 50, savegrid = "D:/GeographicData/HexMap_ISEA4H_res9_aor.shp")

grids9 <- "D:/GeographicData/HexMap_ISEA4H_res9_aor.shp"

temp9 <- readOGR(grids9)

temp9a <- elide(temp9, shift=c(30, 0))

writeOGR(temp9a, "D:/GeographicData/HexMap_ISEA4H_res9_aor_shifted.shp", "HexMap_ISEA4H_res9_aor", driver="ESRI Shapefile")


// Updated Coords:

dggs <- dgconstruct("ISEA",aperture = 4, topology = "HEXAGON", spacing = 40, resround = "nearest", metric = TRUE)

grid <- dgrectgrid(dggs, minlat = 25, minlon = -120, maxlat = 80, maxlon = 30, savegrid = "D:/GeographicData/HexMap_ISEA4H_res8_AtlEur.shp")

grids8 <- "D:/GeographicData/HexMap_ISEA4H_res8_AtlEur.shp"

temp8 <- readOGR(grids8)

> temp8a <- elide(temp8, shift=c(30, 0))

> writeOGR(temp8a, "D:/GeographicData/HexMap_ISEA4H_res8_AtlEur_Shft30Lon.shp", "HexMap_ISEA4H_res8_AtlEur", driver="ESRI Shapefile")


---------

## Updated Methodology (Nov 2022)

### dggs <- dgconstruct("ISEA",aperture = 4, topology = "HEXAGON", spacing = 500, resround = "nearest", metric = TRUE)

> grid <- dgrectgrid(dggs, minlat = 20, minlon = -150, maxlat = 80, maxlon = 50, savegrid = "E:/Projects/HexagonR/Shp/HexMap_ISEA4H_Res4_Wide.shp")
>
> grids4 <- "E:/Projects/HexagonR/Shp/HexMap_ISEA4H_Res4_Wide.shp"
>
> temp4 <- readOGR(grids4)
>
> temp4a <- elide(temp4, shift=c(30, 0))
>
> writeOGR(temp4a, "E:/Projects/HexagonR/Shp/HexMap_ISEA4H_Res4_WideOffset.shp", "HexMap_ISEA4H_Res4_Wide", driver="ESRI Shapefile")

------------

### dggs <- dgconstruct("ISEA",aperture = 4, topology = "HEXAGON", spacing = 250, resround = "nearest", metric = TRUE)

> grid <- dgrectgrid(dggs, minlat = 20, minlon = -150, maxlat = 80, maxlon = 50, savegrid = "E:/Projects/HexagonR/Shp/HexMap_ISEA4H_Res5_Wide.shp")
>
> grids5 <- "E:/Projects/HexagonR/Shp/HexMap_ISEA4H_Res5_Wide.shp"
>
> temp5 <- readOGR(grids5)
>
> temp5a <- elide(temp5, shift=c(30, 0))
>
> writeOGR(temp5a, "E:/Projects/HexagonR/Shp/HexMap_ISEA4H_Res5_WideOffset.shp", "HexMap_ISEA4H_Res5_Wide", driver="ESRI Shapefile")
