<template>
  <div id="app">
    <MyHeader @search='doSearch'/>
    <MyMain :listaFilms="listaFilms" :series="series"/>
  </div>
</template>

<script>
  import MyHeader from './components/MyHeader.vue'
  import MyMain from './components/MyMain.vue'

  const axios = require('axios');

  export default {
    name: 'App',
    components: {
      MyHeader,
      MyMain,
    },
    data() {
      return {
       listaFilms: [],
       series: []
      }
    },
    methods: {

      doSearch(keyword) {
       this.getFilms(keyword)
       this.getTv(keyword)
      },

      getFilms(keyword) {

        axios.get('https://api.themoviedb.org/3/search/movie?api_key=d16c4fcd5c54c5a0cf763754037eaf73&query=' + keyword +'&language=it-IT')
          .then((response)=> {
            this.listaFilms = response.data.results;
          })
          .catch(function (error) {
           console.log(error)
          });
      },

       getTv(keyword) {
       console.log(keyword)

        axios.get('https://api.themoviedb.org/3/search/tv?api_key=d16c4fcd5c54c5a0cf763754037eaf73&query=' + keyword +'&language=it-IT')
          .then((response)=> {
            this.series = response.data.results;
            console.log(this.series)
          })
          .catch(function (error) {
           console.log(error)
      
          });
      }
    }
  }

</script>



<style lang="scss">

@import "src/assets/commonRules.scss"; 

</style>
