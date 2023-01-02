<template>
    <section id="searchForm" v-if="!this.error">
        <div class="searchIcon">
            <img :src="search" alt="magnifying glass icon">
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
        <div v-if="this.error" class="error"> 
            <p>{{this.error}}</p>
            <button @click="refresh" class="return">Go back</button>
        </div>
        <Results v-else-if="clickResults" :info="this.result"/>
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
            showDefault: true, 
            error: null
        }
    },
    methods: {
        getData() {
            axios.get(`https://api.github.com/users/${this.user}`)
                .then(res => 
                    this.result = res.data,
                    this.showResults(),
                    this.removeDefault(),
                    this.user = ''
                )
                .catch(err => 
                    this.error = 'Something went wrong. Please try again or enter a valid username.'
                )
        },
        showResults() {
            this.clickResults = true
        },
        removeDefault() {
            this.showDefault = false
        },
        refresh() {
            window.location.reload()
        }
    }
}
</script>