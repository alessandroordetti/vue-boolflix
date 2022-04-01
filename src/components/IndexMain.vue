<template>
    <main>
        <div class="container">
            <div class="row">
                <div class="" v-for="(element, index) in filmList" :key=index>
                    <FilmCard 
                        :lingua="element.original_language"
                        :titolo="element.original_title"
                        :titoloOriginale="element.original_title"
                        :votoMedio="element.vote_average"
                    />
                </div>
            </div>
        </div>
    </main>
</template>

<script>
import axios from "axios";
import FilmCard from './FilmCard.vue'



export default {
    name: 'IndexMain',

        components: {
        FilmCard,
    },


    data: function(){
        return {
            filmList: '',
        }
    },

    created: function () {
    this.getApi();
    },

    methods: {
    getApi () {
        axios
        .get('https://api.themoviedb.org/3/search/movie?api_key=25cf02f7f319fef92585c5875256324a&language=en-US&page=1&include_adult=false&query=1')
        .then((result)=> {
        this.filmList = result.data.results;
        })
        .catch((error) =>{
        console.error(error);
        })
        }
    },

}
</script>

<style>

</style>