<template>
  <div class="app-container">
    <Settings v-model="size"/>
    <Game :size="size"/>
    <p class="instructions">Try to turn off all the lights.
      When a light is pressed, that light and all adjacent lights are toggled.</p>
    <a class="github" target="_blank" href="https://github.com/DuaneCreates/lights-out">
      <img src="../public/github.svg"/>
    </a>
  </div>
</template>

<script>

import Settings from '@/components/Settings.vue';
import Game from '@/components/Game.vue';

export default {
  name: 'App',
  components: {
    Game,
    Settings,
  },
  data() {
    return {
      size: 5, // n is 5 by default
    };
  },
  methods: {},
};
</script>

<style lang="scss">
body {
  padding: 0;
  margin: 0;
  background-color: #122C34;
}

* {
  box-sizing: border-box;
}

.github {
  position: fixed;
  bottom: 20px;
  right: 20px;

  img {
    height: 50px;
    width: auto;
  }
}

.app-container {
  min-height: 100vh;
  padding: 50px 25px;

  p.instructions {
    margin-top: 100px;
    font-size: 14px;
    color: white;
    text-align: center;
  }
}
</style>
