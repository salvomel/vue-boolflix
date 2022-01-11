<template>
    <div class="single-card">
        <div>
            <span class="titolo">Titolo: </span>
            <span>{{film.title}}</span>
        </div>
        <div>
            <span class="titolo-originale">Titolo originale: </span>
            <span>{{film.original_title}}</span>
        </div>
        <div>
            <span class="lingua">Lingua: </span>
            <span>{{film.title}}</span>
                    
        </div>
        <div>
            <span class="voto">Voto: </span>
            <span>{{film.vote_average}}</span>
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