<template>
    <section class="container">
        <div class="row">
            <div
                class="col-3"
                v-for="film in movies"
                :key="film.id"
            >
                <Film :film="film" />
            </div>
        </div>
    </section>
</template>

<script>
import Film from './Film';

export default {
    name: "Listafilm",
    props: ['movies'],
    components: {
        Film,
    },
}    
</script>

<style lang="scss">

</style>