<template>
  <div id="app">
    <AppHeader @filmResearch="filterVideo($event) "/>
    <AppMain :seriesFilm="nameDvd"/> 
  </div>
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
      nameDvd: [],
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
        this.nameDvd = resp.data.results;
      });
    },
  },
};
</script>

<style lang="scss" scoped>

</style>
