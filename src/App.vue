<template>
  <div class="app-container">
    <Settings v-model="size"/>
    <Game :size="size"/>
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
      size: 5,
    };
  },
  methods: {},
};
</script>

<style lang="scss">
body {
  padding: 0;
  margin: 0;
}

* {
  box-sizing: border-box;
}

.app-container {
  height: 100vh;
  width: 100vw;
  padding-top: 50px;
  background-color: #122C34;
}
</style>
