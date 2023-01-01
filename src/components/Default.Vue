<template>
    <div v-if="this.error"> {{this.error}} </div>
    <Results v-else :info="this.result" />
</template>

<script>
    import axios from 'axios'
    import Results from './Results.vue'

    export default {
        name: 'Default',
        components: { Results },
        data(){
            return {
                user: 'chriskimty',
                result: '',
                error: null
            }
        },
        mounted(){
            axios.get(`https://api.github.com/users/${this.user}`)
                .then(res => (this.result = res.data))
                .catch(err => this.error = 'Something went wrong. Please try again.')
        }
    }
</script>