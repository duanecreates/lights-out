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
.app-container {

}
</style>
