<template>
  <header>
      <div class="logo">Boolflix</div>
      <div class="searchbar-botton">
          <div class="searchbar">
              <input type="text" placeholder="cerca un film"> 
          </div>
          <div class="botton">
              <button>cerca</button>
          </div>
      </div>
  </header>
</template>

<script>
export default {
    nome: 'Header'
}
</script>

<style lang="scss">

header{
    height: 60px;
    background-color: gray;
    display: flex;
    justify-content: space-between;
    align-items: center;
}
.searchbar-botton{
    display: flex;
    
}

</style>