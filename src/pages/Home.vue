<template>
    <div class="section">        
        <div class="container">
            <movies-list title='Recomendados' :movies='movies'/>
        </div>
    </div>
</template>

<script>
import MoviesList from './../components/movie-list/MoviesList'

export default {
    components: { MoviesList },
    props: ['movies']
}
</script>




