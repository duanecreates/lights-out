<template>
  <div class="app-container">
    <Settings v-model="size"/>
  </div>
</template>

<script>

import Settings from '@/components/Settings.vue';

export default {
  name: 'App',
  components: {
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
