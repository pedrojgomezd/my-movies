<template>
  <div id="app">
    <hero @handelSearch='searchMovie'/>
    <home v-if="!movie" :movies='movies'/>
    <detail v-else :movie='movie' />
  </div>
</template>

<script>
import Hero from './components/hero/Hero'
import Home from './pages/Home'
import Detail from './pages/Details'
import {EventBus} from './EventBus'

const URL = 'https://yts.am/api/v2/'

export default {  
  name: 'app',
  components: { Home, Detail, Hero },

  data() {
    return {
      movies: [],
      movie: null
    }
  },
  created() {
    this.fetch()

    EventBus.$on('selectMovie', this.selectMovie)
    EventBus.$on('backHome', () => this.movie = null)
  },

  methods: {
    fetch () {
      axios.get(`${URL}list_movies.json`)
        .then(({data}) => this.movies = data.data.movies)
    },

    selectMovie(movie) {
      this.movie = movie
    },

    searchMovie(title) {
      axios.get(`${URL}list_movies.json?query_term=${title}`)
        .then(({data}) => this.movies = data.data.movies)
    }
  }

}

</script>
