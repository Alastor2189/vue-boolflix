<template>
  <main class="main">
      <ul class="card-list">
        <AppCardMovie v-for="item  in videoFilm" :key="item.id" :video="item"/>
      </ul>
      <ul class="card-list">
        <AppCardMovie v-for="item  in videoSeries" :key="item.id" :video="item"/>
      </ul>
  </main>
</template>

<script>
import AppCardMovie from './AppCardMovie.vue';
export default {
    name: "AppMain",
    components: {
        AppCardMovie,
    },
    props: {
        videoFilm: Array,
        videoSeries: Array,
        
    },
};
</script>

<style lang="scss" scoped>
    .main {
        width: 100%;
        background-color: black;
    }

    .card-list {
        display: flex;
        flex-wrap: wrap;
        list-style: none;
        justify-content: center;
         
    }

    ul {
        display: flex;
        flex-flow: row wrap;
    }
    
</style>