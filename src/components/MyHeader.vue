<template>
  <header>

    <div class="logo">
      <a href="#"> <h2>Boolflix</h2> </a>
    </div>

    <div class="search">
      <input type="text" v-model="searchText" placeholder="Cerca il tuo film preferito">
      <button @click="$emit('search', searchText)">Cerca</button>
    </div>

  </header>
</template>

<script>
  export default {
    name: 'MyHeader',
    data() {
      return {
        searchText: ''
      }
    }
  
  }
</script>

<style scoped lang="scss">

@import "src/assets/commonRules.scss"; 

header {
  a {
    text-decoration: none;
  }
  height: 70px;
  background-color: black;
  display: flex;
  align-items: center;
  justify-content: space-between;
    .search { 
       margin-right: 10px;
    }
    h2 {
      color: red;
      text-transform: uppercase;
      margin-left: 10px;
      font-family: Roboto, Oxygen, Ubuntu, Cantarell, 'Open Sans', 'Helvetica Neue', sans-serif;
    }
}
</style>
