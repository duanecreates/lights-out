<template>
  <div class="settings-container">
    <input type="range" min="3" max="50" :value="modelValue"
           @input="(event) => $emit('update:modelValue', +event.target.value)">
  </div>
</template>

<script>
export default {
  name: 'Settings',
  props: {
    modelValue: Number,
  },
};
</script>

<style lang="scss" scoped>
.settings-container {

}
</style>
