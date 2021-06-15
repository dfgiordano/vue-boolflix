<template>
  <div id="app">
      <Header 
        @search="cercaFilm"
      />
      <main>
        <ListaFilm 
          :movies="movies"
          :serieTv="serieTv"
        />
      </main>
  </div>
</template>

<script>
import axios from 'axios';

import Header from './components/Header';
import ListaFilm from './components/ListaFilm';

export default {
  name: 'App',
  components: {
    Header,
    ListaFilm,
  },
  data: function () {
    return {
      ricerca: '',
      movies: [],
      serieTv: []
    }
  },
  methods: {
    cercaFilm: function (ricercaFilm) {
      this.ricerca = ricercaFilm;
      this.getMovies();
      this.getSeries();
    },
    getSeries() {
      axios
        .get('https://api.themoviedb.org/3/search/tv', {
            params : {
                api_key: "b42cd1206725e3a8b0314f1c43fd3e61",
                query: this.ricerca,
                language: "it-IT",
            }
        })
        .then(
          (result) => {
              this.serieTv = result.data.results;
          }
        )
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
                this.movies = result.data.results;
            }
        );
    },
  }
}
</script>

<style lang="scss">
@import './style/general.scss';

</style>
