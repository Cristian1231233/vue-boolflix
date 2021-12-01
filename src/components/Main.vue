<template>
  <div class="menu">
      <div class="container-menu">
          <Film />
      </div>
  </div>
</template>

<script>

import axios from 'axios';
import Film from './Film.vue'

export default {
    nome: 'Main',
    components:{
        Film
    },
    data() {

    },
    methods: {
        getApi(){
            axios.get('https://api.themoviedb.org/3/search/movie?api_key=db7794d74f6d8ca357ea23c659300bfb&query=ritorno+al+futuro&language=it-IT')
            .then( r => {
                console.log('r',r);
                
            }).catch( e => {
                console.log('e',e);
            })
        }
    }
}
</script>

<style lang="scss">

.container-menu{
    margin-top: 15px;
}

</style>