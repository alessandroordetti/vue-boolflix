<template>
    
        <div class="card p-2 text-center mb-3">
            <div class="card-body">
                <h5 class="card-title">{{titolo}}</h5>
                <img class="immagine-locandina" :src="'https://image.tmdb.org/t/p/w500' + locandina" alt="Immagine Locandina">
                <p class="card-text">{{titoloOriginale}}</p>
                <img :src="'https://flagcdn.com/16x12/' + lingua + '.png'">
                <p class="card-text">{{votoMedio}}</p>
            </div>
        </div>
    
</template>

<script>
export default {
    name: 'FilmCard',

    data: function() {
        return {
            baseImageURL: 'https://image.tmdb.org/t/p/w250',
        }
    },

    props: ['titolo', 'titoloOriginale', 'lingua', 'votoMedio', 'locandina'],
}

</script>

<style lang="scss" scoped>
    .immagine-locandina {
        width: 100%;
    }
</style>