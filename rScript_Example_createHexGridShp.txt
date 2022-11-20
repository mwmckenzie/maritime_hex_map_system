// R Script Example
// Creating and Exporting Shifted Hex Map Shapefiles
// Grid: ISEA4H
// Cell Spacing: 
// Shift:  +30 deg (lon), + 0 deg (lat)
// Example: Creates a hex grid at resolution '9'; clips to lat/lon bounding box (25, -80), (80, 50); saves non-shifted grid to shp, imports and shifts shp by 30 deg longitude; saves shifted grid as shp

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

> grid <- dgrectgrid(dggs, minlat = 20, minlon = -120, maxlat = 80, maxlon = 80, savegrid = "E:/Projects/HexagonR/Shp/HexMap_ISEA4H_Res4_Wide.shp")
> grids4 <- "E:/Projects/HexagonR/Shp/HexMap_ISEA4H_Res4_Wide.shp"
> temp4 <- readOGR(grids4)
