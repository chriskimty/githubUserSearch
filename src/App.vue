<template>
    <Nav />
    <SearchForm />
</template>

<script>
  import SearchForm from './components/SearchForm.vue'
  import Nav from './components/Nav.vue'

  export default {
    name: 'App',
    components: { Nav, SearchForm },
  }
</script>
