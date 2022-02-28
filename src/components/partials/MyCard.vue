<template>

    <li>
        <p>{{film.title}}</p>
        <div>{{film.original_title}}</div>
        <div>{{film.original_language}}</div>
        <div>{{film.vote_average}}</div>
    </li>
  
</template>

<script>
export default {
  name: "MyCard",
  props: {
      "film" : Object    
  }
}
</script>

<style lang="scss" scoped>

</style>