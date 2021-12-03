<template>
  <div class="menu">
      <h2>Film</h2>
      <div class="container-menu">
      
     <div class="card flip-card"
      v-for="(film) in propFilm"
      :key="film.id"
      
      >
     <div class="flip-card-inner">
        
      <div class="flip-card-front">
        <ul>
          <li v-if="film.poster_path"><img class="film" :src="`https://image.tmdb.org/t/p/w342/${film.poster_path}`" alt=""></li>
          <li v-else><p>placeholder img</p></li>
        </ul>
       </div>
       
       <div class="flip-card-back">
        <ul>
          <li>{{film.title}}</li>
          <li>{{film.original_title}}</li>
          <li v-if="film.original_language === 'it' || film.original_language === 'en'"><img class="flag" :src="require(`../assets/${film.original_language}.png`)" alt=""></li>
          <li v-else><p>{{film.original_language}}</p></li>
          <li><i class="fas fa-star"></i></li>
          <li>{{film.vote_average}}--> {{Math.round(film.vote_average / 2)}}</li>
          <li><i v-for="(item,index) in 5"
               :key="index"
               class="fa-star"
              :class="index < Math.round(film.vote_average / 2) ? 'fas' : 'far'"></i>
          </li>
          <li><div class="testo">overview: {{film.overview}}</div></li>
        </ul>
        </div>
      </div>
     </div>
    </div>
      
      <h2>Serie TV</h2>
      <div class="container-menu">
      
      <div class="card2 flip-card"
      v-for="(serie) in serieTv"
      :key="serie.id"
      
      >
      <div class="flip-card-inner">
        <div class="flip-card-front">
        <ul>
          <li v-if="serie.poster_path"><img class="serie" :src="`https://image.tmdb.org/t/p/w342/${serie.poster_path}`" alt=""></li>
          <li v-else><p>placeholder img</p></li>
        </ul>
          </div>
          <div class="flip-card-back">
          <ul>
          <li>{{serie.name}}</li>
          <li>{{serie.original_name}}</li>
          <li v-if="serie.original_language === 'it' || serie.original_language === 'en'"><img class="flag" :src="require(`../assets/${serie.original_language}.png`)" alt=""></li>
          <li v-else><p>{{serie.original_language}}</p></li>
          <!-- <li>{{serie.vote_average}}</li> -->
          <li><i class="fas fa-star"></i></li>
          <li>{{serie.vote_average}}--> {{Math.round(serie.vote_average / 2)}}</li>
          <li><i v-for="(item,index) in 5"
               :key="index"
               class="fa-star"
              :class="index < Math.round(serie.vote_average / 2) ? 'fas' : 'far'"></i>
          </li>
          <li><div class="testo">overview: {{serie.overview}}</div></li>
        </ul>
        </div>
      </div>
     </div>
    </div>
      
      
  </div>
</template>

<script>




export default {
    nome: 'Main',
    data(){
        return{
            arrImag: ['it', 'en']
        }
    },
    props:{
        propFilm: Array,
        serieTv: Array,
    },
    methods:{
       
    }
    
}
</script>

<style lang="scss">
body{
    background-color: #434343;
}
.container-menu{
    display: flex;
    flex-wrap: wrap;
    width: 1200px;
    margin: 15px auto;
}
.card{
    border: 1px solid white;
    ul li{
        list-style: none;
    }
    
    
}
.testo{
    overflow-y: auto;
}
.film, .serie{
    width: 100%;
    height: 100%;
}
.card2{
    
    ul li{
        list-style: none;
    }
    
}

.flag {
    width:30px;
}

/////////////////////////

.flip-card {
  background-color: transparent;
  width: 200px;
  height: 300px;
  perspective: 1000px;
}

.flip-card-inner {
  position: relative;
  width: 100%;
  height: 100%;
  text-align: center;
  transition: transform 0.6s;
  transform-style: preserve-3d;
  box-shadow: 0 4px 8px 0 rgba(0,0,0,0.2);
}

.flip-card:hover .flip-card-inner {
  transform: rotateY(180deg);
}

.flip-card-front, .flip-card-back {
  position: absolute;
  width: 100%;
  height: 100%;
  -webkit-backface-visibility: hidden;
  backface-visibility: hidden;
}

.flip-card-front {
  background-color: black;
  color: black;
}

.flip-card-back {
  background-color: black;
  color: white;
  transform: rotateY(180deg);
}

</style>