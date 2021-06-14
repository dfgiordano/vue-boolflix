<template>
  <div id="app">
    <Header />
    <ListaFilm />
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
    
  }
}
</script>

<style lang="scss">
@import './style/general.scss';

</style>
