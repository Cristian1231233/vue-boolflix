<template>
  <div class="menu">
      <h2>Film</h2>
      <div class="container-menu">
      
     <div class="card"
      v-for="(film) in propFilm"
      :key="film.id"
      
      >
        <ul>
          <li>{{film.title}}</li>
          <li>{{film.original_title}}</li>
          <li><img :src="image" alt=""></li>
          <li>{{film.vote_average}}</li>
        </ul>
    </div>
      </div>
      <h2>Serie TV</h2>
      <div class="container-menu">
      
      <div class="card2"
      v-for="(serie) in serieTv"
      :key="serie.id"
      
      >
        <ul>
          <li>{{serie.name}}</li>
          <li>{{serie.original_name}}</li>
          <li><img :src="image" alt=""></li>
          <li>{{serie.vote_average}}</li>
        </ul>
      </div>
      </div>
      
  </div>
</template>

<script>




export default {
    nome: 'Main',
    data(){
        return{
            
        }
    },
    props:{
        propFilm: Array,
        serieTv: Array,
        image: String
    },
    methods:{
       
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
.card2{
    width: 200px;
    background-color: green;
    ul li{
        list-style: none;
    }
    
}
</style>