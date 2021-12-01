<template>
  <div class="menu">
      <div class="container-menu">
     <div class="card"
      v-for="(film) in propFilm"
      :key="film.id"
      :propFilm="film"
      >
      <ul>
          <li>{{film.title}}</li>
          <li>{{film.original_title}}</li>
          <li>{{film.original_language}}</li>
          <li>{{film.vote_average}}</li>
      </ul>
  </div>
      </div>
  </div>
</template>

<script>




export default {
    nome: 'Main',
    
    props:{
        propFilm: Array
    }
    
}
</script>

<style lang="scss">

.container-menu{
    display: flex;
    flex-wrap: wrap;
    margin-top: 15px;
}
.card{
    width: 200px;
    background-color: green;
    ul li{
        list-style: none;
    }
    
}

</style>