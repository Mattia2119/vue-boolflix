<template>

    <main>
        <MyList :films="listaFilms"/>
    </main>

</template>

<script>

import MyList from "../components/MyList.vue"

export default {
 name: "MyMain",
 props: {
     'listaFilms': Array
     },
 components: {
     MyList
 }
}

</script>

<style lang="scss" scoped>

@import "src/assets/commonRules.scss"; 


</style>