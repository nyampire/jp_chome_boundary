# convert ShapeFile to GeoJSON

    set SHAPE_ENCODING=CP932
    ogr2ogr -s_srs EPSG:4612 -t_srs EPSG:4326 -f geoJSON dst_filne_name.geojson scr_file_name.shp

or

    set SHAPE_ENCODING=CP932
    for %i in (*.shp) do ogr2ogr -s_srs EPSG:4612 -t_srs EPSG:4326 -f geoJSON %~ni.geojson %i 
