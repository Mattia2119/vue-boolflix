<template>
   <section>
    <h1>Lista Film</h1>
    <div class="movie-list">
        <MyCard v-for="(film, index) in films" :key="index" :info='film'/>
    </div>
  </section>

</template>

<script>

import MyCard from './partials/MyCard.vue';

export default {
    name: "FilmList",
    props: {
        'films': Array
    },
    components: {
        MyCard,
    }
}

</script>

<style lang="scss" scoped>

  @import "src/assets/commonRules.scss"; 

</style>