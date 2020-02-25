<template>
  <div>
    {{ MglMap }}
    <mgl-map :accessToken="accessToken" :mapStyle="mapStyle"/>
  </div>
</template>

<script>
  import MapboxGeoCoder from '@mapbox/mapbox-gl-geocoder'
  import Mapbox from 'mapbox-gl'
  import { MglMap } from 'vue-mapbox'

  const ACCESS_TOKEN = 'pk.eyJ1IjoieWtvYmEiLCJhIjoiY2s3MWxrZngyMDcxYzNlcXM4ZnVzbTRoMiJ9.pW6fXCV53omjfT36kpEdOA'
  const MAP_STYLE = 'mapbox://styles/mapbox/streets-v11'
  export default {
    components: {
      MglMap,
    },
    data() {
      return {
        mapbox: null,
        MglMap: MglMap,
        accessToken: ACCESS_TOKEN,
        mapStyle: MAP_STYLE,
      }
    },
    created() {
      this.mapbox = Mapbox
      /*
      this.mapbox.addControl(
        new MapboxGeoCoder({
          accessToken: ACCESS_TOKEN,
          mapboxgl: Mapbox
        })
      )
       */
    },
  }
</script>
