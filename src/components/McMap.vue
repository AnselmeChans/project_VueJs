<template>
  <div id="map-address"></div>
</template>

<script>
import L from "leaflet";
import css from "leaflet/dist/leaflet.css"

export default {
  name: "McMap",

  data(){
    return{
      map: null
    }
  },
  mounted() {
    this.map = L.map('map-address', {
    center: [43.6044622, 1.4442469],
    zoom: 13
});;

    L.tileLayer("https://{s}.tile.openstreetmap.org/{z}/{x}/{y}.png", {
      attribution:
        '&copy; <a href="https://www.openstreetmap.org/copyright">OpenStreetMap</a> contributors'
    }).addTo(this.map);

    // L.marker([100, -0.09])
    //   .addTo(this.map)
    //   .bindPopup("Adresse")
    //   .openPopup();
  }
};
</script>
<style scoped>
  #map-address {
    height: 300px;
    width: 40%
  }
</style>

