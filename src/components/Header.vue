<template>
  <header>
      <div class="logo">Boolflix</div>
      <div class="searchbar-botton">
          <div class="searchbar">
              <input type="text" placeholder="cerca un film" v-model="textSearch" @keyup.enter="$emit('attivaSearch', textSearch)"> 
          </div>
          <div class="botton" @click="$emit('attivaSearch', textSearch)">
              <button>cerca</button>
          </div>
      </div>
  </header>
</template>

<script>
export default {
    nome: 'Header',
    data(){
        return{
            textSearch: ''
        }
    }
}
</script>

<style lang="scss">

header{
    height: 60px;
    background-color: black;
    display: flex;
    justify-content: space-between;
    align-items: center;
    .logo{
        color: rgb(201, 13, 13);
        font-size: 20px;
        text-transform: uppercase;
        margin-left: 20px;
    }
}
.searchbar-botton{
    display: flex;
    
}

</style>