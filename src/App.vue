<template>
  <body>
    <div id="app">
      <AppHeader @filmResearch="filterVideo($event) "/>
      <AppMain :videoFilm="filmDvd" :videoSeries="seriesDvd" /> 
    </div>
  </body>
</template>

<script>
import AppMain from './components/AppMain.vue';
import AppHeader from './components/AppHeader.vue';
import axios from "axios";
export default {
  name: 'App',
  components: {
    AppMain,
    AppHeader, 
  },
  data: function () {
    return {
      filmDvd: [],
      seriesDvd: [],
      researchName: "",
    };
  },
  methods: {
    filterVideo (event) {
      this.researchName = event;
      axios.get("https://api.themoviedb.org/3/search/movie", {
        params: {
          api_key: "43278e63239ef2d508322837f14a75df",
          query: event,
        },
      })
      .then((resp) =>  {
        this.filmDvd = resp.data.results;
      });
      axios.get("https://api.themoviedb.org/3/search/tv", {
        params: {
          api_key:"43278e63239ef2d508322837f14a75df",
          query: event,    
        },
      })
      .then((resp) => {
        this.seriesDvd = resp.data.results;
      })
    },
  },
};
</script>

<style lang="scss" scoped>
  @import "./style/common.scss"
</style>
