<template>
  <button type="button" class="switch-container" :class="{on: isOn}"></button>
</template>

<script>
export default {
  name: 'Switch',
  props: {
    isOn: {
      type: Boolean,
    },
  },
};
</script>

<style lang="scss" scoped>
.switch-container {
  width: 40px;
  height: 40px;
  margin: 1px;
  background-color: #0091AD;
  border: 2px solid black;
  cursor: pointer;
  border-radius: 5px;

  &:active, &:focus {
    outline: none;
  }

  &.on {
    background-color: #44FFD2;
  }
}
</style>
