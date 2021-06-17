<template>
  <div id="app">
      <Header 
        @search="cercaFilm"
      />
      <main>
        <ListaRisultati 
          :movies="movies"
          :serieTv="serieTv"
        />
      </main>
  </div>
</template>

<script>
import axios from 'axios';

import Header from './components/Header';
import ListaRisultati from './components/ListaRisultati';

export default {
  name: 'App',
  components: {
    Header,
    ListaRisultati,
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
        .catch()
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
body {
  background-image: radial-gradient(circle, #a23131, #7a252e, #521c25, #2b1319, #000000);
}

</style>
