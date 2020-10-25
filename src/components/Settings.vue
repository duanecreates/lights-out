<template>
  <div class="settings-container">
    <p>slide to scale grid</p>
    <input type="range" min="3" max="10" :value="modelValue"
           @input="(event) => $emit('update:modelValue', +event.target.value)">
    <p>n = {{ modelValue }}</p>
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

  p {
    font-size: 16px;
    color: white;
  }
}
</style>
