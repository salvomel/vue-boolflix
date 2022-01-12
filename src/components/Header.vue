<template>
    <header>
        <img src="../assets/logo.jpg" alt="Logo">
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
@import '../style/variables';

header {
    background-color: $secondary-color;
    display: flex;
    align-items: center;
    justify-content: space-between;
    padding: 10px 30px;
    
   img {
       height: 50px;
       border-radius: 8px;
    }

   input, .search-btn {
        border: none;
        border-radius: 8px;
        padding: 5px 15px;
    }
    
    input {
        width: 300px;
    }
    
    .search-btn {
        background-color: $primary-color;
        color: $text-color;
        cursor: pointer;
        margin-left: 8px;
    }
}
</style>