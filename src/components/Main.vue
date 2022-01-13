<template>
    <main>
        <div class="container">
            <h2>FILMS</h2>
            <div class="cards-list">
                <FilmCard v-for="film in filmList" :key="film.id" :filmInfo="film" />
            </div>
            <h2>TV SERIES</h2>
            <div class="cards-list">
                <FilmCard v-for="series in seriesList" :key="series.id" :filmInfo="series" />
            </div>
        </div>
    </main>
</template>

<script>
    import FilmCard from './FilmCard.vue';

    export default {
        name: 'Main',
        components: {
            FilmCard,
        },
        props: {
            filmList: Array,
            seriesList: Array
        }
    }
</script>

<style scoped lang="scss">
    @import '../style/main';
</style>
