<template>

    <main>
        <MyList :films="films"/>
    </main>
    
</template>

<script>

import MyList from "../components/MyList.vue"

export default {
 name: "MyMain",
 props: {
     'films': Array
     },
 components: {
     MyList
 }
}

</script>

<style lang="scss" scoped>

@import "src/assets/commonRules.scss"; 


</style>