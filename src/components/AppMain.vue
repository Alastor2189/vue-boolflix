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
        seriesFilm: Object,
    },
};
</script>

<style lang="scss" scoped>

</style>