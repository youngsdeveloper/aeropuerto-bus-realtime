<template>
    <div v-if="loading==false">
        <div id="map-wrap" >
            <client-only>
            <l-map style="height: 600px" :zoom="zoom" :center="center">
                <l-tile-layer :url="url" :attribution="attribution"></l-tile-layer>
                <l-marker :lat-lng="markerLatLng" :icon="icon"></l-marker>
                <l-polyline v-if="showTrail" :lat-lngs="trail" color="#27ae60" weight="10"></l-polyline>

            </l-map>
            </client-only>
        </div>
    </div>
    <div v-else-if="loading">
        <Loading />
    </div>
</template>


<script>
import { latLng, icon } from "leaflet";

export default {


  props: {
      showTrail: {
          type: Boolean,
          default: false
      },
      centerAlways: {
          type: Boolean,
          default: false
      },
  },

  data () {
    return {
      trail: [],
      firstTime: true,
      loading: true,
      url: 'https://{s}.tile.openstreetmap.org/{z}/{x}/{y}.png',
      attribution:
        '&copy; <a target="_blank" href="http://osm.org/copyright">OpenStreetMap</a> contributors',
      zoom: 15,
      center: [51.505, -0.159],
      markerLatLng: [51.504, -0.159],
      icon: icon({
        iconUrl: "images/bus_icon.png",
        iconSize: [50, 50],

      }),

    };
  },

  methods: {
    async fetchLocation(){

      const data = await this.$axios.$get('https://cors-anywhere-youngdeveloper.herokuapp.com/https://www.interbusmurcia.es/ext.aeropuerto.php')
      const location = data.split(",");
      if(this.firstTime || this.centerAlways){
        this.center = location; 
      }
      this.markerLatLng = location;
      this.trail.push(location);

      this.loading=false;
      this.firstTime=false;

    },

    async locationInterval(){
      var ctx = this;
      ctx.fetchLocation();
      setInterval(function () {
        ctx.fetchLocation();
      }, 5000); // Cada 5 segundos
    }
  },
  mounted(){
    this.locationInterval();
  }
}
</script>