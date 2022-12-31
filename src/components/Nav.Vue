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
    cursor: pointer;
  }

  .modeButton {
    background: none;
    border: none;
  }

  .modeButton:hover {
    background: none;
  }

  .modeButton:focus {
    background: none;
  }

  .modeButton img {
    cursor: pointer;
    transition: 0.3s;
  }
</style>