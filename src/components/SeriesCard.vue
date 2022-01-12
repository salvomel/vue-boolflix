<template>
    <div class="single-card">
        <div>
            <span class="title">Nome: {{seriesInfo.name}}</span>
        </div>
        <div>
            <span class="original-title">Nome originale: {{seriesInfo.original_name}}</span>
        </div>
        <div>
            <span v-if="seriesInfo.original_language === 'en'" class="language">Lingua: <img src="../assets/img/en.png" alt="en"></span>
            <span v-else-if="seriesInfo.original_language === 'it'" class="language">Lingua: <img src="../assets/img/it.png" alt="it"></span>
            <span v-else-if="seriesInfo.original_language === 'fr'" class="language">Lingua: <img src="../assets/img/fr.png" alt="fr"></span>
            <span v-else-if="seriesInfo.original_language === 'es'" class="language">Lingua: <img src="../assets/img/es.png" alt="es"></span>
            <span v-else-if="seriesInfo.original_language === 'de'" class="language">Lingua: <img src="../assets/img/de.png" alt="de"></span> 
            <span v-else class="language">Lingua: {{seriesInfo.original_language}}</span>    
        </div>
        <div>
            <span class="vote">Voto: {{seriesInfo.vote_average}}</span>
        </div>
    </div>
</template>

<script>
    export default {
        name: 'SeriesCard',
        props: {
            seriesInfo: Object,
        },
    }
</script>

<style scoped lang="scss">
@import '../style/cards';
</style>