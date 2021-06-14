<template>
    <header>
        <img src="../assets/boolfix.png" alt="boolfix_logo">
        <div>
             <input type="text" placeholder="Cerca...">
            <button>

            </button>
        </div>
    </header>
</template>

<script>
export default {
    name: "Header",
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
        height: 20px;
        width: 50px;
    }
</style>