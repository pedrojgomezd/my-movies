<template>
<div class="hero is-info">
    <div class="hero-body">
        <div class="container">
            <div class="field">
                <p class="control has-icons-left has-icons-right">
                    <input type="text" 
                            class="input is-rounded is-medium" 
                            placeholder="Buscar pelicula..."
                            v-model='search'
                            @keyup.enter='handelSearch'>
                    <span class="icon is-small is-right">
                        <i class="fa fa-search"></i>
                    </span>
                </p>
            </div>
        </div>
    </div>
</div>
</template>

<script>
export default {
    data () {
        return {
            search: ''
        }
    },
    methods: {
        handelSearch(){
            this.$emit('handelSearch', this.search)
        }
    }
}
</script>

