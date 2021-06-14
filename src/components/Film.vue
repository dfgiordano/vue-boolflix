<template>
    <div>
        <h4>{{ film.title }}</h4>
        <h5>{{ film.original_title }}</h5>
        <h6>{{ film.original_language }}</h6>
        <span>{{ film.vote_average }}</span>
    </div>
    
</template>

<script>
export default {
    name: "Film",
    props: ["film"]
}
</script>

<style>

</style>