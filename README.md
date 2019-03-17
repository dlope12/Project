<!DOCTYPE html>
<html>
<head>
  <meta charset="utf-8">
  <meta name="viewport" content="initial-scale=1,maximum-scale=1,user-scalable=no">
  <title>Intro to FeatureLayer - 4.10</title>

  <link rel="stylesheet" href="https://js.arcgis.com/4.10/esri/css/main.css">
  <script src="https://js.arcgis.com/4.10/"></script>

  <style>
    html,
    body,
    #viewDiv {
      padding: 0;
      margin: 0;
      height: 100%;
      width: 100%;
    }
  </style>

  <script>
    require([
        "esri/Map",
        "esri/views/MapView",
        "esri/layers/FeatureLayer"
      ],
      function(
        Map, MapView,
        FeatureLayer
      ) {

        var map = new Map({
          basemap: "hybrid"
        });

        var view = new MapView({
          container: "viewDiv",
          map: map,

          extent: { // autocasts as new Extent()
            xmin: -9177811,
            ymin: 4247000,
            xmax: -9176791,
            ymax: 4247784,
            spatialReference: 102100
          }
        });

        /********************
         * Add feature layer
         ********************/

        // Carbon storage of trees in Warren Wilson College.
        var featureLayer = new FeatureLayer({
          url: "https://geodesy.noaa.gov/storm_archive/storms/tilesa/services/tileserver.php/wmts"
        });

        map.add(featureLayer);

      });
  </script>
</head>

<body>
  <div id="viewDiv"></div>
</body>

</html>
