<template>
   <section class="movies-container">

        <ul>
         <MyCard v-for="(film, index) in films" :key="index" :film="film"/>
        </ul>

   </section>
</template>

<script>

import MyCard from './partials/MyCard.vue';

export default {
    name: "MyList",
    props: {
        'films': Array
    },
    components: {
        MyCard
    }
}

</script>

<style lang="scss" scoped>

@import "src/assets/commonRules.scss"; 

</style>