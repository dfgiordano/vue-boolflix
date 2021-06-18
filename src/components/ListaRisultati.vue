<template>
    <div>
        <section 
            class="movies container"
            v-if="movies.length > 0"
        >
            <div class="row">
                <h2>Film</h2>
                <div
                    class="col-3"
                    v-for="film in movies"
                    :key="film.id"
                >
                    <Film 
                    :film="film"
                    />
                </div>
            </div>
        </section>
        <section 
            class="series container"
            v-if="serieTv.length > 0"
        >
            <div class="row">
                <h2>Serie TV</h2>
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
    </div>
    
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
@import '../style/general.scss';
@import '../style/variables.scss';

    .col-3 {
        margin: 40px 0;
    }
    h2 {
        color: $main_color;
    }
</style>