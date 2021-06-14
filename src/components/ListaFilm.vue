<template>
    <section>
        
    </section>
</template>

<script>
import axios from 'axios';

export default {
    name: "Listafilm",
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
                (res) => {
                    console.log(res);
                }
            );
    }
}    
</script>

<style lang="scss">

</style>