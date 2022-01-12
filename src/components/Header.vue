<template>
    <header>
        <div class="logo">
            <img src="../assets/img/logo.jpg" alt="Logo">
            <h1>BOOLFLIX</h1>
        </div>
        <div>
            <input type="text" placeholder="Cerca un film o una serie TV" v-model="searchText">
            <button @click="$emit('searchClicked', searchText)" class="search-btn">Cerca</button>
        </div>
    </header>
</template>

<script>
export default {
    name: 'Header',
    data: function () {
        return {
            searchText: "",
        }
    }
}
</script>

<style scoped lang="scss">
    @import '../style/header';
</style>