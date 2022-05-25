<template>
    <li class="menu-card">
        <div class="card">
          <h2> {{ video.title }}</h2>
          <h4> {{ video.original_title  }}</h4> 
        <div class="flag">
            <div v-if="video.original_language === 'it'">
            <h4>Lingua:</h4>
            <span :class="`fi fi-it`"></span>
            </div>
            <div v-else-if="video.original_language === 'es'">
            <h4>Lingua:</h4>
            <span :class="`fi fi-es`"></span>
            </div>
            <div v-else-if="video.original_language === 'en'">
            <h4>Lingua:</h4>
            <span :class="`fi fi-gb`"></span>
            </div>
            <div v-else-if="video.original_language === 'ja'">
            <h4>Lingua:</h4>
            <span :class="`fi fi-jp`"></span>
            </div>
            <div v-else-if="video.original_language === 'fr'">
            <h4>Lingua:</h4>
            <span :class="`fi fi-fr`"></span>
            </div>
            <div v-else>
            <h4>Lingua:</h4>
            </div>
            <p> {{ video.original_language  }}</p>
        </div>
          
          <p> {{ video.vote_average }}</p>
        </div>
        <div class="image">
            <img
          :src="`https://image.tmdb.org/t/p/w342/${video.poster_path}`"
          :alt="video.title"
        />
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
@import "~flag-icons/css/flag-icons.css";
@import '~@fortawesome/fontawesome-free/css/all.min.css';
    .menu-card {
        width: calc(100% / 4 - 8px);
        margin: 4px;
        padding: 1em;
        border: 1px solid black;
        text-align: center;
    }
    
</style>