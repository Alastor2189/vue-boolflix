<template>
  <header class="header">
      <div class="title">
          <div class="logo">
              <img src="../assets/gianflix.png" alt="">
          </div>
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
    .header {
        display: flex;
        align-items: center;
        width: 90%;
        margin: 0 auto;
    }

   .search{
       display: flex;
        justify-content: flex-end;
    }
    .title, .search {
        width: 50%;
    }
</style>