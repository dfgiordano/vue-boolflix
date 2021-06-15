<template>
    <section class="container">
        <div class="row">
            <div
                class="col-3"
                v-for="film in movies"
                :key="film.id"
            >
                <Film 
                :film="film"
                />
            </div>
            <div
                class="col-3"
                v-for="serie in serieTv"
                :key="serie.id"
            >
                <SerieTv 
                :serie="serie"
                />
            </div>
        </div>
    </section>
</template>

<script>
import Film from './Film';
import SerieTv from './SerieTv';

export default {
    name: "Listafilm",
    props: ['movies',
            'serieTv'],
    components: {
        Film,
        SerieTv,
    },
}    
</script>

<style lang="scss">

</style>