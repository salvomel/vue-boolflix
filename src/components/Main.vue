<template>
    <main>
        <div class="container">
            <div class="film-list">
                <FilmCard v-for="(film, index) in filmList" :key="index" :filmInfo="film" />
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
        }
    }
</script>

<style scoped lang="scss">
    
    main {
        .container {
            padding: 20px;

            .film-list {
                display: flex;
                flex-wrap: wrap;
            }
        }
    }
</style>

