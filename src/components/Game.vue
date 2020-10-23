<template>
  <div class="game-container">
    <div v-for="y in size" :key="y" class="game-row">
      <div v-for="(cell, x) in grid[y-1]" :key="x" class="game-cell" :class="{on: cell === 1}">

      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Game',
  props: {
    size: {
      type: Number,
    },
  },
  data() {
    return {
      grid: [],
    };
  },
  methods: {
    setup() {
      function generateGridRow(n, rate) {
        const row = [];

        for (let i = 0; i < n; i++) {
          row.push(Math.random() > rate ? 0 : 1);
        }

        return row;
      }

      function hasAnyOn(grid) {
        for (let y = 0; y < grid.length; y++) {
          for (let x = 0; x < grid.length; x++) {
            if (grid[y][x] === 1) {
              return true;
            }
          }
        }

        return false;
      }

      const rate = .05;

      do {
        this.grid = [];

        for (let n = 0; n < this.size; n++) {
          this.grid.push(generateGridRow(this.size, rate));
        }
      } while (!hasAnyOn(this.grid));
    },
  },
  watch: {
    size() {
      this.setup();
    },
  },

  mounted() {
    this.setup();
  },
};
</script>

<style lang="scss" scoped>
.game-container {
  display: flex;
  flex-direction: column;
  flex-wrap: wrap;

  .game-row {
    display: flex;
    flex-direction: row;

    .game-cell {
      width: 40px;
      height: 40px;
      margin: 5px;
      background-color: darkgreen;

      &.on {
        background-color: greenyellow;
      }
    }
  }
}
</style>
