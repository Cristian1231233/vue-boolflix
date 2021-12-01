<template>
  <div class="menu">
      <div class="container-menu">
     <div class="card"
      v-for="(film) in propFilm"
      :key="propFilm.id"
      >
      <ul>
          <li></li>
          <li>Titolo originale</li>
          <li>Lingua</li>
          <li>Voto</li>
      </ul>
  </div>
      </div>
  </div>
</template>

<script>




export default {
    nome: 'Main',
    data(){
        films: propFilm
    },
    props:{
        propFilm: Array
    }
    
}
</script>

<style lang="scss">

.container-menu{
    display: flex;
    margin-top: 15px;
}
.card{
    width: 200px;
    background-color: green;
    
}

</style>