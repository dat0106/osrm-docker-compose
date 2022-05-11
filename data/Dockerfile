FROM osrm/osrm-backend:latest

ADD build.sh .
ADD ./vn_car.osm.pbf /data/vn_car.osm.pbf


RUN apt-get update
RUN apt-get install -y wget

ENTRYPOINT ["./build.sh"]
