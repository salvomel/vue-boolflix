<template>
    <div class="single-card">
        <div>
            <span class="title">Titolo: {{filmInfo.title}}</span>
        </div>
        <div>
            <span class="original-title">Titolo originale: {{filmInfo.original_title}}</span>
        </div>
        <div>
            <span class="language">Lingua: {{filmInfo.original_language}}</span>     
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
@import '../style/variables';

    .single-card {
        color: $text-color;
        margin: 20px;
    }
    
</style>