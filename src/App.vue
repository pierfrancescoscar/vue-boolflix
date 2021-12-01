<template>
  <div id="app">
    <!-- Header -->
    <Header @search="result" />
    <!-- Main Content - Cards -->
    <Main :films="filmList" :series="seriesList" />
  </div>
</template>

<script>
import axios from 'axios';
import Header from '@/components/Header.vue';
import Main from '@/components/Main.vue';

export default {
  name: 'App',
  components: {
    Header,
    Main,
  },
  data() {
    return {
      filmList: null,
      userSearch: '',
      seriesList: null,
    }
  },

  created() {
    this.getFilm();
  },

  methods: {

    result(el) {
      this.userSearch = el;
      this.getFilm();
    },

    getFilm() {
      if(this.userSearch !== '') {

      axios
      .get('https://api.themoviedb.org/3/search/movie',{
          params: {
            api_key: '06e31ba117d5c07092db635756cfaedd',
            query: this.userSearch,
          }
      })

      .then(result => {
        this.filmList = result.data.results;
      })

      axios
      .get('https://api.themoviedb.org/3/search/tv', {
        params: {
          api_key: '06e31ba117d5c07092db635756cfaedd',
          query: this.userSearch,
        }
      })

      .then(result => {
        this.seriesList = result.data.results;
      })
      .catch(err => console.log(err));
    }
      }
     
    
    
  }
}
</script>

<style lang="scss">
#app {
  font-family: 'Poppins', sans-serif;
}

</style>
