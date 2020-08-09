# uos_geoserver

< 서울, 스마트 > 세미나 시리즈
오픈소스 GIS 웹 퍼블리싱 스터디 (GeoServer)

<!doctype html>
<html lang="en">
  <head>
    <link rel="stylesheet" href="https://cdn.jsdelivr.net/gh/openlayers/openlayers.github.io@master/en/v6.4.3/css/ol.css" type="text/css">
    <style>
      .map {
        height: 400px;
        width: 100%;
      }
    </style>
    <script src="https://cdn.jsdelivr.net/gh/openlayers/openlayers.github.io@master/en/v6.4.3/build/ol.js"></script>
    <title>OpenLayers example</title>
  </head>
  <body>
    <h2>My Map</h2>
    <div id="map" class="map"></div>
    <script type="text/javascript">
      var map = new ol.Map({
        target: 'map',
        layers: [
          new ol.layer.Tile({
            source: new ol.source.OSM()
			})
			,new ol.layer.Tile({
            source: new ol.source.TileWMS({
              url: 'http://localhost:8080/geoserver/wms',
              params: {'LAYERS': 'uos:countour'}
            })
          })
        ],
        view: new ol.View({
          center: ol.proj.fromLonLat([127, 37.6]),
          zoom: 9
        })
      });
    </script>
  </body>
</html>
