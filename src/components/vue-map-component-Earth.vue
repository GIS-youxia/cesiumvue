<template>

  <div id="mapView"></div>

</template>

<script>

export default {
  data() {
    return {
      map: {}
    }
  },
  components: {},
  created() { },
  mounted() {
    Cesium.Ion.defaultAccessToken = 'eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJqdGkiOiI3NTZkYjJiOC1hM2U5LTQ4YzgtYmRjNi1iZDMyNWM2YjA3YzQiLCJpZCI6ODgzNDMsImlhdCI6MTY1MjAwMzg3N30.3EZhF6qVxwyyurNgyDqq7q3EthMmnSem6H8jpwnh8-s';
     var esri = new Cesium.ArcGisMapServerImageryProvider({                                         //ArcGIS影像
         url:'https://services.arcgisonline.com/ArcGIS/rest/services/World_Imagery/MapServer'
     })
    var viewer = new Cesium.Viewer('mapView', {
      imageryProvider: esri,
      geocoder: false,
      homeButton: false,
      sceneModePicker: false,
      baseLayerPicker: false,
      navigationHelpButton: false,
      shouldAnimate: false,
      animation: false,
      selectionIndicator: false,
      timeline: false,
      sceneMode: Cesium.SceneMode.SCENE3D,
     
    })
            viewer.dataSources.add(
            Cesium.GeoJsonDataSource.load(
                "../CHN_adm0.json"
            )
        )
     viewer.camera.setView({
             destination:Cesium.Cartesian3.fromDegrees(113.34,34.33,4000000),
             orientation:{
                 heading:Cesium.Math.toRadians(0),
                 pitch:Cesium.Math.toRadians(-90),
                 roll:0,
              
             }
         })
  },
  computed: {},
  methods: {
    initMap() {

    },
  }
}

</script>
<style>
.cesium-viewer-bottom{
  display: none;
}
#mapView{
  margin: 0;
  width: 100%;
  height: 10.05rem;
}
</style>