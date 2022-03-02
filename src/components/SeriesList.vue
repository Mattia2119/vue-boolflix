<template>
  <section>
      <h1>Lista Serie</h1>
    <ul>
        <MyCard v-for="(serie, index) in series" :key="index" :info='serie'/>
    </ul>
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