10/26/2018 Updated GLWD Wetlands Processing

Here are the steps I took (in ARCGIS) to create the new GLWD layer that's replaced the old GLWD in envStack_v3RLB

1) Clip the full GLWD global raster to the ecoregional extent
2) Create two rasters, one of the mosaic (% wetland) classes, the other with all other classes.
2) Reclassify all other wetland types to 1
3) Reproject to same unprojected coordinate systems as snap raster
4) Focal statistics (SUM) calculated at the resolution of envStack (20x20 cells, which scales with latitude)
5) Resample to snap raster resolution based on centerpoint of focal statistics.
7) Reproject and resample the moasic wetland classes to match envstack
6) Recode mosaic wetland classes (50-75 and 75-100% wetland) to 300 and 150, the mid points of their ranges.

Final units are precent cover of wetlands within each un-equal area pixel, oceans are coded 0, the same as 0% wetland. 

