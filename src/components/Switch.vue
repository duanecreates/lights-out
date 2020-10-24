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
  margin: 5px;
  background-color: darkgreen;
  border: none;
  cursor: pointer;

  &:active, &:focus {
    outline: none;
  }

  &.on {
    background-color: greenyellow;
  }
}
</style>
