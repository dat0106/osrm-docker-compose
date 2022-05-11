FROM osrm/osrm-backend:latest

# ADD http://download.geofabrik.de/north-america/us/hawaii-140101.osm.pbf /data/hawaii-140101.osm.pbf
ADD ./vn_car.osm.pbf /data/vn_car.osm.pbf


#http://download.geofabrik.de/north-america/us/hawaii-140101.osm.pbf

RUN ["osrm-extract", "-p", "/opt/car.lua", "/data/vn_car.osm.pbf"]

RUN ["osrm-partition", "/data/vn_car.osrm"]

RUN ["osrm-customize", "/data/vn_car.osrm"]

ENTRYPOINT ["osrm-routed", "--algorithm", "mld"]

CMD ["/data/vn_car.osrm"]

VOLUME ["/data"]

EXPOSE 5000
