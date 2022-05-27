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
            <div class="content-text">
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
                    <p class="language"> {{ video.original_language  }}</p>
                    <p class="vote"> {{ video.vote_average }}</p>
                    <p>
                        <i v-for="n in 5" :key="n" class="fa-star" :class="n <= voteStars ? 'fas' : 'far' "></i>
                    </p>
                    <p>
                        {{ video.overview }}
                    </p>
            </div>
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
        margin: 3px;
        border: 1px solid black;
      
    }

    .text-card {
        color: white;
        display: none;
    }

    .content-text{
        display: flex;
        flex-direction: column;
        justify-content: flex-start;
        margin: 0;

        
        p, h2, h4 {
            margin: 2px;
        }
    }



   

    .image img{
        max-width: 100%;
        object-fit: cover;
    }

    li:hover .text-card {
    display: block;
    overflow-y: scroll;
    height: 240px;
    }
    li:hover .image {
        display: none;
        background-color: rgba(0, 0, 0, 0.8);
    }

    .vote{
        display: none;
    }
    .language{
        text-transform: uppercase;
    }

    i{
        color: gold;
    }


    
</style>