<template>
    <header>
        <img src="../assets/img/logo.jpg" alt="Logo">
        <div>
            <input type="text" placeholder="Cerca un film" v-model="searchText">
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