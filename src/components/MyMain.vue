<template>
    <main>
        <h4>Film</h4>
        <MyList/> 
    </main>
</template>

<script>

import MyList from './partials/MyList.vue'

export default {
 name: "MyMain",
 components: {
     MyList,
 }
}

</script>

<style lang="scss" scoped>

@import "src/assets/commonRules.scss"; 

main {
    background-color: grey;
    height: 1000px;
       .movies-container {
          border: 1px solid white;
          height: 600px;
          width: 90%;
          margin: auto;
           .movie-box {
               height: 12px;
           }
      }
      h4 {
          margin-left: 5%;
          padding-top: 3%;
      }
}

</style>