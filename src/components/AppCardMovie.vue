<template>
    <li class="menu-card">
        <div class="image">
            <img v-if="video.poster_path"
             :src="`http://image.tmdb.org/t/p/w500/${video.poster_path}`"
             :alt="video.title ? video.title : video.name"
            />
            <img v-else src="../assets/no_image.png" alt="Not Image">
        </div>
        <div class="text-card">
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
                
            </div>
            <p> {{ video.original_language  }}</p>
            <p> {{ video.vote_average }}</p>
            <p>
                <i v-for="n in 5" :key="n" class="fa-star" :class="n <= voteStars ? 'fas' : 'far' "></i>
             </p>
        </div> 
        
    </li>
  
</template>

<script>
export default {
    name: 'AppCardMovie',
    props: {
        video: Object,
    },

    computed: {
        voteStars () {
            return Math.ceil(this.video.vote_average / 2);
        }
    },
};
</script>

<style lang="scss" scoped>
@import "~flag-icons/css/flag-icons.css";
@import '~@fortawesome/fontawesome-free/css/all.min.css';
    .menu-card {
        width: calc(100% / 6 - 8px);
        margin: 4px;
        border: 1px solid black;
        text-align: center;
        position: relative;
        max-height: 350px;
        min-height: 350px;
    }
    .text-card {
        position: absolute;
        top: 50%;
        left: 50%;
        transform: translate(-50%, -50%);
        overflow-y: auto;
        display: none;
    }

    .text-card h2, .card h4, .card p {
        margin: 1px;
    }

    .image{
        position: absolute;
    }

    .image img{
        width: 100%;
        height: 100%;
    }

    li:hover .text-card {
    display: block;
}
    li:hover .image {
  display: none;
}
    
</style>