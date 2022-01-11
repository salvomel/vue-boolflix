<template>
    <div class="single-card">
        <div>
            <span class="title">Titolo: {{film.title}}</span>
        </div>
        <div>
            <span class="original-title">Titolo originale: {{film.original_title}}</span>
        </div>
        <div>
            <span class="language">Lingua: {{film.original_language}}</span>     
        </div>
        <div>
            <span class="vote">Voto: {{film.vote_average}}</span>
        </div>
    </div>
</template>

<script>
    export default {
        name: 'FilmCard',
        props: {
            film: Object,
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