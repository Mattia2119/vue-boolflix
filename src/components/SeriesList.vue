<template>
  <section>
      <h1>Lista Serie</h1>
    <div class="movie-list">
        <MyCard v-for="(serie, index) in series" :key="index" :info='serie'/>
    </div>
  </section>

</template>

<script>

import MyCard from './partials/MyCard.vue';

export default {
    name: "SeriesList",
    props: {
        'series': Array
    },
    components: {
        MyCard,
    }
}

</script>

<style lang="scss" scoped>

@import "src/assets/commonRules.scss"; 

</style>