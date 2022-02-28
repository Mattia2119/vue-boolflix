<template>

    <ul>
        <MyCard v-for="(film, index) in films" :key="index" :film='film'/>
    </ul>

</template>

<script>

import MyCard from './partials/MyCard.vue';

export default {
    name: "MyList",
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