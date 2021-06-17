<template>
    <header>
        <a href="#">
            <img src="../assets/boolflix.png" alt="boolflix_logo">
        </a>
        <form >
            <input 
            type="text" 
            placeholder="Cerca..."
            @keyup="$emit('search', ricercaFilm)"
            v-model="ricercaFilm">
        </form>
        <form action="">
            <button
            @click.prevent="$emit('search', ricercaFilm)">
                Cerca
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
@import '../style/general.scss';
@import '../style/variables.scss';
    header {
        display: flex;
        justify-content: space-between;
        align-items: center;
        padding: 0 30px;
        height: 100px;
        background-color: $bg_color;
            input {
                width: 650px;
                border-radius: 5px;
                outline: 0;
                color: $main_color;
            }
            button {
                height: 40px;
                width: 70px;
                border: none;
                border-radius: 5px;
                background-color: $main_color;
                color: white;
                    &:hover {
                        background-color: white;
                        color: $main_color;
                        cursor: pointer;
                    }
            }
    }
</style>