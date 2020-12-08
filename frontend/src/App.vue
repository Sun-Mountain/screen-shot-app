<template>
  <div id="app" class="container">
    <div class="row">
      <div class="col-md-6 offset-md-3 py-5">
        <h1>Generate a thumbnail of a website</h1>

        <form v-on:submit.prevent="makeWebsiteThumbnail">
          <div class="form-group">
            <input v-model="websiteUrl" type="text" id="website-imput" placeholder="Enter a website" class="form-control">
          </div>
          <div class="form-group">
            <button class="btn btn-pramary">Generate!</button>
          </div>
        </form>
      </div>
      <div class="thumbnail-container">
        <img :src="thumbnailUrl"/>
      </div>
    </div>
  </div>
</template>

<script>
import axios from 'axios';

export default {
  name: 'App',
  
  data() { return {
    websiteUrl: '',
    thumbnailUrl: '',
  } },

  methods: {
    makeWebsiteThumbnail() {
      axios.post("https://screenshotapi.net/api/v1/screenshot", {
        url: this.websiteUrl,
      })
      .then((response) => {
        this.thumbnailUrl = response.data.screenshot;
      })
      .catch((err) => {
        console.log(`The API returned an error: ${err}`);
      })
    }
  }
}
</script>

<style lang="scss">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
.thumbnail-container {
  width: 300;

  img {
    max-width:100%;
    max-height: auto;
  }
}
</style>
