<template>
    <div class="single-card">
        <div class="poster" >
            <img :src="`https://image.tmdb.org/t/p/w185/${filmInfo.poster_path}`" :alt="filmInfo.title">
        </div>
        <div class="title">
            <h5>Titolo:</h5>
            <h4>{{filmInfo.title}}</h4>
        </div>
        <div class="original-title">
            <h5>Titolo originale:</h5>
            <h4>{{filmInfo.original_title}}</h4>
        </div>
        <div class="language">
            <span v-if="filmInfo.original_language === 'en'">Lingua: <img src="../assets/img/en.png" alt="en"></span>
            <span v-else-if="filmInfo.original_language === 'it'">Lingua: <img src="../assets/img/it.png" alt="it"></span>
            <span v-else-if="filmInfo.original_language === 'fr'">Lingua: <img src="../assets/img/fr.png" alt="fr"></span>
            <span v-else-if="filmInfo.original_language === 'es'">Lingua: <img src="../assets/img/es.png" alt="es"></span>
            <span v-else-if="filmInfo.original_language === 'de'">Lingua: <img src="../assets/img/de.png" alt="de"></span> 
            <span v-else>Lingua: {{filmInfo.original_language}}</span>    
        </div>
        <div class="vote">
            <h5>Voto:</h5>
            <h4>{{filmInfo.vote_average}}</h4>
        </div>
    </div>
</template>

<script>
    export default {
        name: 'FilmCard',
        props: {
            filmInfo: Object,
        },
    }
</script>

<style scoped lang="scss">
    @import '../style/cards';
</style>