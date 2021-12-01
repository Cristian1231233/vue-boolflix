<template>
  <div>
   <Header />
   <Main :films="propFilm" />
  </div>
</template>

<script>
// import HelloWorld from './components/HelloWorld.vue'
import Header from './components/Header.vue'
import Main from './components/Main.vue'
import axios from 'axios';

export default {
  name: 'App',
  components: {
    Header,
    Main
  },
  data() {
        return{
            films: []
        }
    },
    methods: {
        getApi(){
            axios.get('https://api.themoviedb.org/3/search/movie?api_key=db7794d74f6d8ca357ea23c659300bfb&query=ritorno+al+futuro&language=it-IT')
            .then( r => {
                console.log('response',r);
                this.films = r.data.results;
                console.log(this.films);

            }).catch( e => {
                console.log('e',e);
            })
        }
    },
    mounted() {
        this.getApi();
    },
  
}
</script>

<style lang="scss">



*{
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

</style>
