<template>
  <header>

    <div class="logo">
      <h2>Boolflix</h2>
    </div>

    <div class="search">
      <input type="text" placeholder="Cerca il tuo film preferito">
      <button>Cerca</button>
    </div>

  </header>
</template>

<script>
export default {
  name: 'MyHeader',
 
}
</script>

<style scoped lang="scss">

@import "src/assets/commonRules.scss"; 

header {
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
