<template>
  <header class="header">
      <div class="title">
          <h2>
              Boolflix
          </h2>
      </div>
      <div class="search">
          <input type="text" placeholder="Cerca un film/serie Tv" v-model="searchVideo">
          <button @click="$emit('filmResearch', searchVideo)">
            Invia
          </button>
      </div>

  </header>
</template>

<script>
export default {
    name: 'AppHeader',
    data() {
        return {
            searchVideo:"",
        }
    },
    methods: {
        searchList () {

        },
    },
};
</script>

<style lang="scss" scoped>

</style>