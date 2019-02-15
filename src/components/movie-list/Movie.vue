<template>
    <div>
        <div class="movie">
            <div class="left">
                <figure class="image">
                    <img :src="movie.medium_cover_image" alt="">
                </figure>
            </div>
            <div class="rigth">
                <p class="title is-6">
                    <a href="#" @click="selected">
                        {{ movie.title_long }}
                    </a>
                </p>
                <p class="subtitle is-6">
                    <span v-for='(genre, index) in movie.genres' :key="index"> {{ genre }} |</span>
                </p>
                <p class="subtitle is-5">
                    {{ movie.rating }} <i class="fa fa-star"></i>
                </p>
            </div>
        </div>
    </div>
</template>
<script>
import { EventBus } from './../../EventBus'

export default {
    props: ['movie'],
     created() {
     },
     methods: {
        selected(){
            console.log('click')
            EventBus.$emit('selectMovie', this.movie)
        }
    }
}
</script>

<style>
.movie {
    background: #fff;
    display: flex;
    flex-direction: row;
    width: 250px;
    margin: 5px;

}
.left > figure {
    width: 90px;

}

.rigth {
    padding: 10px;
}
</style>
