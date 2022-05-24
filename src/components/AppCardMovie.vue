<template>
    <li class="menu-card">
        <div class="card">
          <h2> {{ video.title }}</h2>
          <h4> {{ video.original_title  }}</h4> 
          <p> {{ video.original_language  }}</p>
          <p> {{ video.vote_average }}</p>
        </div>
    </li>
  
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
    .menu-card {
        width: calc(100% / 4 - 8px);
        margin: 4px;
        padding: 1em;
        border: 1px solid black;
        text-align: center;
    }
    
</style>