<template>

        <div class="card p-2 text-center mb-3" >
            <div class="card-body">
                    <div class="img-wrapper">
                        <img class="immagine-locandina" :src="'https://image.tmdb.org/t/p/w342' + locandina">
                    </div>

                    

                    <div class="informazioni-contenuto">
                        <h5 class="card-title">{{titolo}}</h5>
                        <p class="card-text">{{titoloOriginale}}</p>
                        <p class="descrizione">{{descrizione}}</p>
                        <img :src="'https://flagcdn.com/16x12/' + lingua + '.png'">
                        <p class="card-text">{{votoMedio}}</p>
                        <div class="voto d-inline" v-for="(n) in mediaVoto(votoMedio)" :key="n">   
                            <span> &#9733; </span>
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

    props: ['titolo', 'titoloOriginale', 'lingua', 'votoMedio', 'locandina', 'descrizione'],
}

</script>

<style lang="scss" scoped>
    .immagine-locandina {
        width: 100%;
    }

    .descrizione {
        max-height: 100px;
        overflow-y: auto;
        width: 100%;
    }

    .informazioni-contenuto {
        display: none;
    }

    .card:hover {
        .card {
            max-width: 100%;
        }

        & .img-wrapper {
            display: none;
        }

        & .informazioni-contenuto {
            display: block;
        }
    }
</style>