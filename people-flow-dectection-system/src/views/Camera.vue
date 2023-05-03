<template>
  <div>
    <base-header class="pb-6 pb-8 pt-5 pt-md-8 bg-gradient-success">
      <!-- Card stats -->
      <!-- Card stats -->
      <b-row>
        <b-col xl="3" md="6">
          <stats-card title="实时人数"
                      type="gradient-red"
                      sub-title="78"
                      icon="ni ni-air-baloon"
                      class="mb-4">

            <template slot="footer">
              <span class="text-success mr-2">2.98%</span>
              <span class="text-nowrap">相比于一个小时前</span>
            </template>
          </stats-card>
        </b-col>
        <b-col xl="3" md="6">
          <stats-card title="进入监控区域人数"
                      type="gradient-orange"
                      sub-title="56"
                      icon="ni ni-bold-right"
                      class="mb-4">

            <template slot="footer">
              <span class="text-success mr-2">10.97%</span>
              <span class="text-nowrap">相比于一个小时前</span>
            </template>
          </stats-card>
        </b-col>
        <b-col xl="3" md="6">
          <stats-card title="离开监控区域人数"
                      type="gradient-green"
                      sub-title="24"
                      icon="ni ni-bold-left"
                      class="mb-4">

            <template slot="footer">
              <span class="text-danger mr-2">5.72%</span>
              <span class="text-nowrap">相比于一个小时前</span>
            </template>
          </stats-card>

        </b-col>
        <b-col xl="3" md="6">
          <stats-card title="平均停留时间 (s)"
                      type="gradient-info"
                      sub-title="37.8"
                      icon="ni ni-time-alarm"
                      class="mb-4">

            <template slot="footer">
              <span class="text-success mr-2">24.8%</span>
              <span class="text-nowrap">相比于一个小时前</span>
            </template>
          </stats-card>
        </b-col>
      </b-row>
    </base-header>

    <b-container fluid class="mt--7">
      <b-row>
        <b-col>
          <b-card no-body class="border-0">
            <div id="map-custom" class="map-canvas"
                 style="height: 600px;"></div>
          </b-card>
        </b-col>
      </b-row>
    </b-container>
  </div>
</template>
<script>
  // import { API_KEY } from './Maps/API_KEY';
  // import GoogleMapsLoader from 'google-maps';

  // GoogleMapsLoader.KEY = API_KEY;

  // export default {
  //   methods: {
  //     initMap(google) {
  //       let map, lat = 40.748817, lng = -73.985428, color = "#5e72e4";
  //       map = document.getElementById('map-custom');

  //       let myLatlng = new google.maps.LatLng(lat, lng);
  //       let mapOptions = {
  //         zoom: 12,
  //         scrollwheel: false,
  //         center: myLatlng,
  //         mapTypeId: google.maps.MapTypeId.ROADMAP,
  //         styles: [{
  //           "featureType": "administrative",
  //           "elementType": "labels.text.fill",
  //           "stylers": [{ "color": "#444444" }]
  //         }, {
  //           "featureType": "landscape",
  //           "elementType": "all",
  //           "stylers": [{ "color": "#f2f2f2" }]
  //         }, {
  //           "featureType": "poi",
  //           "elementType": "all",
  //           "stylers": [{ "visibility": "off" }]
  //         }, {
  //           "featureType": "road",
  //           "elementType": "all",
  //           "stylers": [{ "saturation": -100 }, { "lightness": 45 }]
  //         }, {
  //           "featureType": "road.highway",
  //           "elementType": "all",
  //           "stylers": [{ "visibility": "simplified" }]
  //         }, {
  //           "featureType": "road.arterial",
  //           "elementType": "labels.icon",
  //           "stylers": [{ "visibility": "off" }]
  //         }, {
  //           "featureType": "transit",
  //           "elementType": "all",
  //           "stylers": [{ "visibility": "off" }]
  //         }, { "featureType": "water", "elementType": "all", "stylers": [{ "color": color }, { "visibility": "on" }] }]
  //       }

  //       map = new google.maps.Map(map, mapOptions);

  //       let marker = new google.maps.Marker({
  //         position: myLatlng,
  //         map: map,
  //         animation: google.maps.Animation.DROP,
  //         title: 'Hello World!'
  //       });

  //       let contentString = '<div class="info-window-content"><h2>Argon Dashboard PRO</h2>' +
  //         '<p>A beautiful premium dashboard for Bootstrap 4.</p></div>';

  //       let infowindow = new google.maps.InfoWindow({
  //         content: contentString
  //       });

  //       google.maps.event.addListener(marker, 'click', function () {
  //         infowindow.open(map, marker);
  //       });
  //     }
  //   },
  //   mounted() {
  //     GoogleMapsLoader.load(google => {
  //       this.initMap(google);
  //     });
  //   }
  // };
</script>
