<template>
    <nav class="devNav">
      <h1>devfinder</h1>
      <div class="modeSwitch">
        <!-- later, need to make both dynamic, and make div clickable -->
        <p>light</p>
        <div class="modeIconBox">
          <img :src="modeIcon" alt="">
        </div>
      </div>
    </nav>
    <SearchForm />
</template>

<script>
import modeIcon from '../src/assets/icon-sun.svg'
import modeIcon2 from '../src/assets/icon-moon.svg'
import SearchForm from './components/SearchForm.vue'

export default {
  name: 'App',
  components: { SearchForm },
  data() {
    return {
      modeIcon: modeIcon,
    }
  }
}
</script>

<style>
  .devNav {
    display: flex;
    justify-content: space-between;
    align-items: center;
  }
  .devNav h1 {
    font-size: 2.6rem;
    font-weight: bold;
  }
  .devNav p {
    font-size: 1.3rem;
    letter-spacing: 2.5px;
    text-transform: uppercase;
  }
  .modeSwitch {
    display: flex;
    align-items: center;
    gap: 15px;
  }
</style>
