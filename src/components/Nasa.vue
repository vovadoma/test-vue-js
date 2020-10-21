<template>
  <div>
    <h1>Nasa API</h1>
  </div>
</template>

<script>

import axios from "axios";

export default {
  name: 'Nasa',
  props: {},
  data() {
    return {
      marsPhotos: [],
      marsPhotosApiUrl: 'https://api.nasa.gov/mars-photos/api/v1/rovers/curiosity/photos?sol=1000&page=1&api_key=DEMO_KEY',
    };
  },
  methods: {
    getApiData() {
      axios({
        url: this.marsPhotosApiUrl,
        method: 'GET'
      }).then((response) => {
        const dataPage = response.data;
        console.log(dataPage);
      });
    }
  },
  computed: {

  },
  beforeMount() {
    this.getApiData();
  },
  mounted() {
  }
}
</script>

<style scoped>
</style>
