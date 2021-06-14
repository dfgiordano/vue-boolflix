<template>
  <div id="app">
      <Header 
        @search="cercaFilm"
      />
      <main>
        <ListaFilm :movies="movies" />
      </main>
  </div>
</template>

<script>
import Header from './components/Header'
import ListaFilm from './components/ListaFilm.vue'
import axios from 'axios'

export default {
  name: 'App',
  components: {
    Header,
    ListaFilm,
  },
  data: function () {
    return {
      ricerca: '',
      movies: []
    }
  },
  methods: {
    cercaFilm: function (ricercaFilm) {
      this.ricerca = ricercaFilm;
      this.getMovies();
    },
    getMovies() {
      axios
        .get('https://api.themoviedb.org/3/search/movie', {
            params : {
                api_key: "b42cd1206725e3a8b0314f1c43fd3e61",
                query: this.ricerca,
                language: "it-IT",
            }
        })
        .then(
            (result) => {
                // console.log(result.data.results);
                this.movies = result.data.results;
                // console.log(this.ElencoFilm);
            }
        );
    }
  }
}
</script>

<style lang="scss">
@import './style/general.scss';

</style>
