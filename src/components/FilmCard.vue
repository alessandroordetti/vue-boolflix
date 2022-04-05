<template>
    
    <div>
        <div class="card p-2 text-center mb-3" >
            <div class="card-body">
                <div v-if="locandina !== null" class="img">
                    <img class="immagine-locandina" :src="'https://image.tmdb.org/t/p/w500' + locandina">
                </div>

                <div class="description">
                    <h5 class="card-title">{{titolo}}</h5>
                    <p class="card-text">{{titoloOriginale}}</p>
                    <img :src="'https://flagcdn.com/16x12/' + lingua + '.png'">
                    <p class="card-text">{{votoMedio}}</p>

                    <div class="voto d-inline" v-for="(n) in mediaVoto(votoMedio)" :key="n">   
                        <span> &#9733; </span>
                    </div>
                </div>
            </div>
        </div>
    </div>

        
    
</template>

<script>
export default {
    name: 'FilmCard',

    data: function() {
        return {
            
        }
    },

    methods: {
    mediaVoto(votoMedio){
    return parseInt (votoMedio/ 2)
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