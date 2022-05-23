<template>
  <div class="card">
      <ul class="menu-card">
          <li> {{ video.title }}</li>
          <li> {{ video.original_title  }}</li> 
          <li> {{ video.original_language  }}</li>
          <li> {{ video.vote_average }}</li>

      </ul>

  </div>
</template>

<script>
export default {
    name: 'AppCardMovie',
    props: {
        video: Object,
    }
}
</script>

<style lang="scss" scoped>

</style>