<template>
    <div class="movies">
        <img 
            class="copertina"
            :src="`https://image.tmdb.org/t/p/w342` + `${film.poster_path}`" 
            :alt="`${film.title}`"
        >
        <h4>
            <a href="#"> {{ film.title }} </a>
        </h4>
        <h5>
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
        <!-- <div>
            <a href="#"> {{ Math.ceil(film.vote_average * 0.2) }} </a>
        </div> -->
        <span>
            <i
                v-for="i in 5"
                :key="i"
                :class="i <= starCount() ? 'fas fa-star' : 'far fa-star'"
            ></i>
        </span>
    </div>
</template>

<script>
export default {
    name: "Film",
    props: ["film"],
    methods: {
        starCount: function() {
        return Math.round(this.film.vote_average / 2);
        }
    }
}
</script>

<style lang="scss" scoped>
@import '../style/general.scss';

    a {
        text-decoration: none;
    }
    .flags {
        height: 20px;
        width: 40px;
        border: 1px solid black;
    }
    .copertina {
        height: 300px;
    }
</style>