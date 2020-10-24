<template>
  <div class="won-container" @click="$emit('play-again')">
    <h1>You Won!</h1>
    <p>Play Again</p>
  </div>
</template>

<script>
export default {
  name: 'Win',
};
</script>

<style lang="scss" scoped>
.won-container {
  text-align: center;
  cursor: pointer;

  h1, p {
    color: white;
  }
}
</style>
