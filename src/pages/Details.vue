<template>
<div class="section">
    <div class='container'>
        <div class="columns">
            <div class="column is-two-thirds">
                <div class="video">
                    <iframe width="560" height="315" :src="`https://www.youtube.com/embed/${movie.yt_trailer_code}`" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
                </div>
            </div>
            <div class="columns">
               <button @click='backHome'>Regresa</button>
            </div>
        </div>
    </div>
</div>
</template>
<script>
import { EventBus } from './../EventBus'

export default {
    props: ['movie'],

    methods: {
        backHome () {
            EventBus.$emit('backHome')
        }
    }
}
</script>

<style>
iframe {
    height: 315px;
}
.video {
}
</style>

