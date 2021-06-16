<template>
    <div class="serie_tv">
        <img class="copertina" 
            :src="`https://image.tmdb.org/t/p/w342` + `${serie.poster_path}`" 
            :alt="`${serie.original_name}`">
        <h4>
            <a href="#"> {{ serie.name }} </a>
        </h4>
        <h5>
            <a href="#"> {{ serie.original_name }} </a>
        </h5>
        <div v-if=" serie.original_language == 'it' ">
            <a href="#">
                <img class="flags" src="../assets/it.png" alt="italian_flag">
            </a>
        </div>
        <div v-else-if=" serie.original_language == 'en' ">
            <a href="#">
                <img class="flags" src="../assets/en.png" alt="english_flag">
            </a>
        </div>
        <div v-else-if=" serie.original_language == 'es' ">
            <a href="#">
                <img class="flags" src="../assets/es.png" alt="spanish_flag">
            </a>
        </div>
        <div v-else-if=" serie.original_language == 'pt' ">
            <a href="#">
                <img class="flags" src="../assets/pt.png" alt="portugal_flag">
            </a>
        </div>
        <div v-else-if=" serie.original_language == 'ru' ">
            <a href="#">
                <img class="flags" src="../assets/ru.png" alt="russian_flag">
            </a>
        </div>
        <div v-else-if=" serie.original_language == 'fr' ">
            <a href="#">
                <img class="flags" src="../assets/fr.jpeg" alt="french_flag">
            </a>
        </div>
        <div v-else-if=" serie.original_language == 'de' ">
            <a href="#">
                <img class="flags" src="../assets/de.jpg" alt="german_flag">
            </a>
        </div>
        <div v-else>
            <a href="#"> {{ serie.original_language }} </a>
        </div>
        <div>
            <a href="#"> {{ serie.vote_average }} </a>
        </div>
    </div> 
</template>

<script>
export default {
    name: "SerieTv",
    props: ["serie"],
}
</script>

<style lang="scss" scoped>
    a {
        text-decoration: none;
    }
    .flags {
        height: 20px;
        width: 40px;
        border: 1px solid black;
    }
    .copertina {
        height: 200px;
    }

</style>