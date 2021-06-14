<template>
  <div id="app">
      <Header 
      @search="cercaFilm"
      />
      <main>
        <ListaFilm />
      </main>
  </div>
</template>

<script>
import Header from './components/Header'
import ListaFilm from './components/ListaFilm.vue'

export default {
  name: 'App',
  components: {
    Header,
    ListaFilm,
  },
  data: function () {
    return {
      ricerca: '',
    }
  },
  methods: {
    cercaFilm: function (ricercaFilm) {
      console.log("clic sul pulsante ricerca");
      console.log(ricercaFilm);
      ricercaFilm = this.ricerca;
    }
  },
  computed: {
    filmFiltrati: function () {
      const nuovoArrayFilm = this.ListaFilm.filter(
        (element) => {
          return element.title.includes(this.ricerca);
        }
      );
      return nuovoArrayFilm;
  },
},
}
</script>

<style lang="scss">
@import './style/general.scss';

</style>
