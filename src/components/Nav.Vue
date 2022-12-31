<template>
    <nav class="devNav">
      <h1>devfinder</h1>
      <div @click="switchMode" class="modeSwitch">
        <p v-if="nightMode">light</p>
        <p v-else>dark</p>
        <div class="modeIconBox">
            <button class="modeButton">
                <img v-if="nightMode" :src="lightIcon" alt="sun icon">
                <img v-else :src="darkIcon" alt="moon icon">
            </button>
        </div>
      </div>
    </nav>
</template>

<script>
import lightIcon from '../assets/icon-sun.svg'
import darkIcon from '../assets/icon-moon.svg'

export default {
    name: 'Nav',
    data() {
        return {
        lightIcon,
        darkIcon,
        nightMode: false
    }
  },
  methods: {
    switchMode(){
        this.nightMode = !this.nightMode
    }
  }
}
</script>
