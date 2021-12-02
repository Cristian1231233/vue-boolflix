<template>
  <div>
   <Header @attivaSearch = "ricercaDeiFilm" />
   <Main :propFilm="films" :serieTv="serieTv" />
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
            films: [],
            title: '',
            serieTv: [],
            
        }
    },
    methods: {
        getApi(){
            axios.get(`https://api.themoviedb.org/3/search/movie?api_key=db7794d74f6d8ca357ea23c659300bfb&query=${this.title}&language=it-IT`)
            .then( r => {
                console.log('response',r);
                this.films = r.data.results;
                console.log(this.films);

            }).catch( e => {
                console.log('e',e);
            })
        },
        getApi2(){
            axios.get(`https://api.themoviedb.org/3/search/tv?api_key=db7794d74f6d8ca357ea23c659300bfb&query=${this.title}&language=it_IT`)
            .then( r => {
                console.log('response',r);
                this.serieTv = r.data.results;
                console.log('serieTv',this.serieTv);

            }).catch( e => {
                console.log('e',e);
            })
        },
        ricercaDeiFilm(textSearch){
          
          console.log(textSearch);
          this.title = textSearch;
          console.log('title',this.title);
          
          this.getApi();
          this.getApi2()
        }
    },
    mounted() {
        this.getApi();
        this.getApi2();
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
