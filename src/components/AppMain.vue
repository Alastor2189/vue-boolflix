<template>
  <main class="main">
      <AppCardMovie v-for="(item, index) in seriesFilm" :key="index" :movie="item"/>
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
        display: flex;
        flex-wrap: wrap;
        background-color: black;
    }
</style>