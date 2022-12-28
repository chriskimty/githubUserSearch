<template>
    <Results :info="this.result"/>
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
                result: ''
            }
        },
        mounted(){
            axios.get(`https://api.github.com/users/${this.user}`)
                .then(res => (this.result = res.data))
                // add better error handling after
                .catch(err => console.log(err.message))
        }
    }
</script>