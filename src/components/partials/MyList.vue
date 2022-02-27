<template>
   <section class="movies-container">



            <div class="movie-box">
                <h4></h4>
                <h4></h4>
                <p></p>
                <p></p>
            </div>




        </section>
</template>

<script>

//Integro Axios//
const axios = require('axios');

export default {
    name: "MyList",

 data() {
     return {
         listaFilm: []
     }
 },
 methods: {
     getMovies() {
        axios.get('https://api.themoviedb.org/3/search/movie?api_key=d16c4fcd5c54c5a0cf763754037eaf73&query=StarWars&language=it-IT')

        .then((response) => {
            this.listaFilm = response.data.results[1];
            console.log(this.listaFilm);
        })
        .catch(function (error) {
            // handle error
            console.log(error);
        })
        .then(function () {
            // always executed
        });
     }
  },
  created() {
      this.getMovies();
  }
}

</script>



<style lang="scss" scoped>

@import "src/assets/commonRules.scss"; 

.movie-box {
    height: 300px;
    width: calc(100% / 5);
    border: 1px solid white;
}

</style>