<template>
  <main class="main">
      <ul class="card-list">
        <AppCardMovie v-for="item  in seriesFilm" :key="item.id" :video="item"/>
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
        seriesFilm: Array,
    },
};
</script>

<style lang="scss" scoped>
    .main {
        width: 80%;
        margin: 0 auto;
       
        background-color: lightblue;
    }

    .card-list {
        display: flex;
        flex-wrap: wrap;
        list-style: none;
    }

    
</style>