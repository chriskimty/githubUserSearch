<template>
    <section id="searchForm">
        <div class="searchIcon">
            <img :src="search" alt="">
        </div>
        <form @submit.prevent="getData" class="form">
            <label class="sr-only">Search Github Username</label>
            <input 
            type="text"
            v-model="user"
            placeholder="Search Github username..."
            required/>
            <button>Search</button>
        </form>
    </section>

    <section id="searchResults">
        <Default v-if="showDefault"/>
        <Results v-if="clickResults" :info="this.result"/>
    </section>
    
</template>

<script>
import axios from 'axios'
import Results from './Results.vue'
import Default from './Default.vue'
import search from '../assets/icon-search.svg'

export default {
    name: 'SearchForm',
    components: { Results, Default },
    data() {
        return {
            user: null,
            result: '',
            search: search,
            clickResults: false,
            showDefault: true
        }
    },
    methods: {
        getData() {
            axios.get(`https://api.github.com/users/${this.user}`)
                .then(res => (this.result = res.data))
                // add better error handling after
                .catch(err => console.log(err.message))
            this.showResults()
            this.removeDefault()
        },
        showResults() {
            this.clickResults = true
        },
        removeDefault() {
            this.showDefault = false
        }
    }
}
</script>

<style>
#searchForm {
    display: flex;
}

button {
    cursor: pointer;
}
</style>