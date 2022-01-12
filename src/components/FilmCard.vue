<template>
    <div class="single-card">
        <div>
            <span class="title">Titolo: {{filmInfo.title}}</span>
        </div>
        <div>
            <span class="original-title">Titolo originale: {{filmInfo.original_title}}</span>
        </div>
        <div>
            <span v-if="filmInfo.original_language === 'en'" class="language">Lingua: <img src="../assets/img/en.png" alt="en"></span>
            <span v-else-if="filmInfo.original_language === 'it'" class="language">Lingua: <img src="../assets/img/it.png" alt="it"></span>
            <span v-else-if="filmInfo.original_language === 'fr'" class="language">Lingua: <img src="../assets/img/fr.png" alt="fr"></span>
            <span v-else-if="filmInfo.original_language === 'es'" class="language">Lingua: <img src="../assets/img/es.png" alt="es"></span>
            <span v-else-if="filmInfo.original_language === 'de'" class="language">Lingua: <img src="../assets/img/de.png" alt="de"></span> 
            <span v-else class="language">Lingua: {{filmInfo.original_language}}</span>    
        </div>
        <div>
            <span class="vote">Voto: {{filmInfo.vote_average}}</span>
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