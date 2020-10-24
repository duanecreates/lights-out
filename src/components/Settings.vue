<template>
  <div class="settings-container">
    <p><small>slide to scale grid</small></p>
    <input type="range" min="3" max="10" :value="modelValue"
           @input="(event) => $emit('update:modelValue', +event.target.value)">
    <p><small>n = {{ modelValue }}</small></p>
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
  display: flex;
  flex-direction: column;
  align-items: center;

  p small {
    color: white;
  }
}
</style>
