<template>
  <div id="app">
    <Header @searchClicked="search" />
    <Main :filmList="films"/>
  </div>
</template>

<script>
import axios from 'axios';
import Header from "./components/Header.vue";
import Main from "./components/Main.vue";

export default {
  name: "App",
  components: {
    Header,
    Main
  },
  data: function () {
    return {
      films: [],
      apiKey: '24c04ef549dc063d6f67e72a4486f9a3',
      queryValue: "",
    };
  },
  methods: {
    search: function(userString) {
      this.queryValue = userString;
      this.getFilm();
    },
    // Chiamata API film
    getFilm: function() {
      axios.get("https://api.themoviedb.org/3/search/movie", {
        params: {
          api_key: this.apiKey,
          query: this.queryValue,
        }
      })
      .then((response) => {
        this.films = response.data.results;
      });
    }
    
  }
};
</script>

<style lang="scss">
  @import './style/general';
</style>
