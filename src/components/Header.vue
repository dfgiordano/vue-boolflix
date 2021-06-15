<template>
    <header>
        <a href="#">
            <img src="../assets/boolflix.png" alt="boolflix_logo">
        </a>
        <form >
            <input 
            type="text" 
            placeholder="Cerca..."
            v-model="ricercaFilm">
            <button
            @click.prevent="$emit('search', ricercaFilm)">
                cerca
            </button>
        </form>
    </header>
</template>

<script>
export default {
    name: "Header",
    data: function () {
       return {
           ricercaFilm: ''
       } 
    },
}
</script>

<style lang="scss">
    header {
        display: flex;
        justify-content: space-between;
        align-items: center;
        padding: 0 30px;
        height: 100px;
        background-color: yellow;
    }
    button {
        height: 30px;
        width: 50px;
    }
</style>