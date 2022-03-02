<template>

    <main>
        <MyList :films="listaFilms"/>
        <SeriesList :series="series"/>
    </main>

</template>

<script>

import MyList from "../components/MyList.vue"
import SeriesList from "../components/SeriesList.vue"

export default {
 name: "MyMain",
 props: {
     'listaFilms': Array,
     'series': Array

     },
 components: {
     MyList,
     SeriesList
 }
}

</script>

<style lang="scss" scoped>

@import "src/assets/commonRules.scss"; 


</style>