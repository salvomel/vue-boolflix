<template>
    <div class="single-card">

        <!-- Se poster non presente mostra avviso e titolo film/serie-->
        <div class="poster">
            <img v-if="filmInfo.poster_path" :src="`https://image.tmdb.org/t/p/w342/${filmInfo.poster_path}`" :alt="filmInfo.title ? filmInfo.title : filmInfo.name">
            <div v-else class="no-img">*Poster non disponibile*
                <div>{{filmInfo.title ? filmInfo.title : filmInfo.name}}</div>
            </div>
        </div>

        <div class="back-card">

            <div class="title">
                <h5>Titolo:</h5>
                <h4>{{filmInfo.title ? filmInfo.title : filmInfo.name}}</h4>
            </div>

            <!-- Titolo/Nome originale da mostrare solo se diverso dal titolo/nome -->
            <div v-if="filmInfo.original_title !== filmInfo.title || filmInfo.original_name !== filmInfo.name" class="original-title">
                <h5>Titolo originale:</h5>
                <h4>{{filmInfo.original_title ? filmInfo.original_title : filmInfo.original_name}}</h4>
            </div>

            <div class="language">
                Lingua:
                <span v-if="flags.includes(filmInfo.original_language)">
                    <img :src="require(`../assets/img/${filmInfo.original_language}.png`)" :alt="filmInfo.original_language">
                </span>
                <span v-else>{{filmInfo.original_language}}</span>    
            </div>

            <!-- Se voto non presente mostra avviso -->
            <h5 class="vote">Voto:</h5>
            <div v-if="filmInfo.vote_average">
                <span v-for="i in 5" :key="i">
                    <i v-if="i <= getVote(filmInfo.vote_average)" class="fas fa-star stars"></i>
                    <i v-else class="far fa-star"></i>
                </span>
            </div>
            <span v-else class="no-vote">*Votazione non disponibile*</span>

            <!-- Se descrizione non presente mostra avviso -->
            <h5 class="overview">Descrizione:</h5>
            <div>
                <span v-if="filmInfo.overview">{{filmInfo.overview}}</span>
                <span v-else>~Descrizione non disponibile~</span>
            </div>
        </div>
    </div>
</template>

<script>
    export default {
        name: 'FilmCard',
        data: function() {
            return {
                flags: ['en', 'it', 'fr', 'es', 'de']
            };
        },
        props: {
            filmInfo: Object,
        },
        methods: {
            // Funzione arrotondamento per eccesso
            getVote(vote) {
                return Math.ceil(vote / 2); 
            }
        }
    }
</script>

<style scoped lang="scss">
    @import '../style/cards';
</style>