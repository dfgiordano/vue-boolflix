<template>
    <div class="movies">
        <div class="container_img">
            <img 
                v-if="film.poster_path != null"
                class="copertina"
                :src="`https://image.tmdb.org/t/p/w342` + `${film.poster_path}`" 
                :alt="film.title"
            >
            <img
                class="copertina"
                v-else
                src="https://d994l96tlvogv.cloudfront.net/uploads/film/poster/poster-image-coming-soon-placeholder-no-logo-500-x-740_23763.png" 
                :alt="film.name"
            >
            <div class="container_testo">
                <h4> Titolo&colon;
                    <a href="#"> {{ film.title }} </a>
                </h4>
                <h5> Titolo originale&colon;
                    <a href="#"> {{ film.original_title }} </a>
                </h5>
                <div v-if=" film.original_language == 'it' ">
                    <a href="#">
                        <img 
                            class="flags" 
                            src="../assets/it.png" 
                            alt="italian_flag">
                    </a>
                </div>
                <div v-else-if=" film.original_language == 'en' ">
                    <a href="#">
                        <img 
                            class="flags" 
                            src="../assets/en.png" 
                            alt="english_flag"
                        >
                    </a>
                </div>
                <div v-else-if=" film.original_language == 'es' ">
                    <a href="#">
                        <img 
                            class="flags" 
                            src="../assets/es.png" 
                            alt="spanish_flag"
                        >
                    </a>
                </div>
                <div v-else-if=" film.original_language == 'pt' ">
                    <a href="#">
                        <img 
                            class="flags" 
                            src="../assets/pt.png" 
                            alt="portugal_flag"
                        >
                    </a>
                </div>
                <div v-else-if=" film.original_language == 'ru' ">
                    <a href="#">
                        <img 
                            class="flags" 
                            src="../assets/ru.png" 
                            alt="russian_flag"
                        >
                    </a>
                </div>
                <div v-else-if=" film.original_language == 'fr' ">
                    <a href="#">
                        <img 
                            class="flags" 
                            src="../assets/fr.jpeg"
                            alt="french_flag"
                        >
                    </a>
                </div>
                <div v-else-if=" film.original_language == 'de' ">
                    <a href="#">
                        <img  
                            class="flags" 
                            src="../assets/de.jpg" 
                            alt="german_flag"
                        >
                    </a>
                </div>
                <div v-else>
                    <a href="#"> {{ film.original_language }} </a>
                </div>
                <div>
                    <i
                        v-for="i in 5"
                        :key="i"
                        :class="i <= starCount() ? 'fas fa-star' : 'far fa-star'"
                    ></i>
                </div>
                <h5 
                    v-if="film.overview != '' "> 
                        Overview&colon;
                        <span class="overview">{{ film.overview }}</span>
                </h5>
                <h5 v-else>
                        Overview&colon;
                        <span class="overview">Scrivi la prima recensione per questo titolo!</span>
                </h5>
            </div>
        </div>   
    </div>
</template>

<script>
export default {
    name: "Film",
    props: ["film"],
    data: function () {
        return {
            bandiere: ['it','en','es','de','pt','ru','fr']
        }
    },
    methods: {
        starCount: function() {
        return Math.ceil(this.film.vote_average / 2);
        }
    }
}
</script>

<style lang="scss" scoped>
@import '../style/general.scss';
@import '../style/variables.scss';

    a {
        text-decoration: none;
            .flags {
            height: 20px;
            width: 40px;
            border: 1px solid $bg_color;
        }
    }
    
    .copertina {
        height: 400px;
        width: 250px;
        border: 1px solid $bg_color;
            &:hover{
                opacity: 0;
            }
    }
    .copertina_vuota {
        width: 342px;
    }
    .container_img {
        position: relative;
    }
    .container_testo {
        display: flex;
        flex-flow: column;
        width: 250px;
        height: 400px;
        padding: 20px;
        position: absolute;
        top: 0;
        left:0;
        z-index: -1;
        cursor: pointer;
        overflow: hidden;
        background-color: $bg_color;
        color: $text_color;
            a {
                font-size: 12px;
                color: $text_color;
            }
            h4,h5 {
                margin: 0;
                font-size: 14px;
                display:inline;
                color: $title_color; 
                    span {
                        color: $text_color;
                    }
            }
            i {
                color: gold;
            }
            .overview {
                font-size: 12px;
            }
    }
</style>