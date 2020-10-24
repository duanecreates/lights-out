<template>
  <div class="app-container">
    <Settings v-model="size"/>
    <Game :size="size"/>
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
  position: absolute;
  bottom: 20px;
  right: 20px;

  img {
    height: 50px;
    width: auto;
  }
}

.app-container {
  height: 100vh;
  width: 100vw;
  padding-top: 50px;
}
</style>
