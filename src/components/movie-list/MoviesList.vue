<template>
<div>
    <h3 class="title is-4 has-text-grey	">{{ title }}</h3>
    <div class="movies-list">
        <movie v-for='(movie, index) in movies' 
                :key='index' 
                :movie='movie' />
    </div>
</div>
</template>

<script>
import Movie from './Movie'
export default {
    components: { Movie },
    props: ['title', 'movies'],
    methods: {
    }
}
</script>


<style>
body {
    background: #ddd;
}
.movies-list {
    display: flex;
    flex-flow: row wrap;
    justify-content: space-around;
    overflow-x: auto;
}
</style>