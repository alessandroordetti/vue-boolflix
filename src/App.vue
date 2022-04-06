<template>
  <div id="app">
    <IndexHeader @cercaFilm='nuovaRicerca' />

    <IndexMain :filmList="filmList" :serieList="serieList" />

  </div>
</template>

<script>
import axios from "axios";

import IndexHeader from './components/IndexHeader.vue';
import IndexMain from './components/IndexMain.vue';


export default {
  name: 'App',
  components: {
    IndexHeader,
    IndexMain
  }, 

  data: function(){
    return {
      filmList: [],
      serieList: []
    }
  },

  methods: {
    nuovaRicerca (cercaFilm) {
      
      axios.get(`https://api.themoviedb.org/3/search/movie?api_key=25cf02f7f319fef92585c5875256324a&query=${cercaFilm}`).then((result)=> {
            this.filmList = result.data.results;
            console.log(this.filmList);
            })
            .catch((error) =>{
            console.error(error);
            })

            axios.get(`https://api.themoviedb.org/3/search/tv?api_key=25cf02f7f319fef92585c5875256324a&query=${cercaFilm}`).then((result)=> {
            this.serieList = result.data.results;
            console.log(this.serieList);
            })
            .catch((error) =>{
            console.error(error);
            })
    },
  }
}
</script>

<style lang="scss">
@import '@/style/main-style.scss';
  
</style>
