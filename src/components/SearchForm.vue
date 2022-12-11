<template>
    <div id="searchForm">
        <div class="searchIcon">
            <img :src="search" alt="">
        </div>
        <form @submit.prevent="handleSubmit" class="form">
            <label class="sr-only">Search Github Username</label>
            <input type="text" placeholder="Search Github username..."/>
            <button>Search</button>
        </form>
    </div>
</template>

<script>
import search from '../assets/icon-search.svg'
export default {
    data() {
        return {
            search: search
        }
    },
    methods: {
            handleSubmit(){
                console.log("submitted")
            }
        }
}
</script>

<style>
#searchForm {
    display: flex;
}
</style>