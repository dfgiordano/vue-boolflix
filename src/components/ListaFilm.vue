<template>
    <section class="container">
        <div class="row">
             <div class="col-3" v-for="film in ElencoFilm"
            :key="film.id">
            <Film
            :film="film" 
            />
            </div>
        </div>
       
        
    </section>
</template>

<script>
import axios from 'axios';
import Film from './Film';

export default {
    name: "Listafilm",
    components: {
        Film,
    },
    data: function() {
        return {
            ElencoFilm: [],
        }
    },
    created: function () {
        axios
            .get('https://api.themoviedb.org/3/search/movie', {
                params : {
                    api_key: "b42cd1206725e3a8b0314f1c43fd3e61",
                    query: "pirati",
                    language: "it-IT",
                }
            })
            .then(
                (result) => {
                    // console.log(result.data.results);
                    this.ElencoFilm = result.data.results;
                    // console.log(this.ElencoFilm);
                }
            );
    }
}    
</script>

<style lang="scss">

</style>