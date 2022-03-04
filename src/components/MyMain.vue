<template>

    <main>
        <FilmList :films="listaFilms"/>
        <SeriesList :series="series"/>
    </main>

</template>

<script>

import FilmList from "../components/FilmList.vue"
import SeriesList from "../components/SeriesList.vue"

export default {
 name: "MyMain",
 props: {
     'listaFilms': Array,
     'series': Array

     },
 components: {
     FilmList,
     SeriesList
 }
}

</script>

<style lang="scss" scoped>

@import "src/assets/commonRules.scss"; 

main {
    max-width: 1100px;
    margin: 0 auto;
}


</style>