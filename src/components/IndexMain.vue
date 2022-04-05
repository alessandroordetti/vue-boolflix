<template>
    <main >
        <div class="container">

            <div class="row row-cols-5">
                <div v-for="(element, index) in filmList" :key=index class="col my-4">
                    <FilmCard
                        :locandina="element.poster_path"
                        :lingua="element.original_language"
                        :titolo="element.original_title"
                        :titoloOriginale="element.original_title"
                        :votoMedio="element.vote_average"
                    />
                </div>
            </div>

            <div class="row row-cols-5">
                <div v-for="(element, index) in serieList" :key=index class="col">
                    <FilmCard 
                        :locandina="element.poster_path"
                        :lingua="element.original_language"
                        :titolo="element.original_name"
                        :titoloOriginale="element.name"
                        :votoMedio="element.vote_average"
                    />
                </div>
            </div>
        </div>
    </main>
</template>

<script>
/* import axios from "axios";
 */import FilmCard from './FilmCard.vue'



export default {
    name: 'IndexMain',

        components: {
        FilmCard,
    },

    props: {
        'filmList': Array,
        'serieList': Array
    },


    data: function(){
        return {
            filmListArray: [],
        }
    },

    methods: {

    },

}
</script>

<style lang="scss" scoped>

</style>