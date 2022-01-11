<template>
    <main>
        <div class="container">
            <div class="film-list">
                <FilmCard v-for="(film, index) in film" :key="index" :film="film" />
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
            film: Array,
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

