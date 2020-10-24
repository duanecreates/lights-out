<template>
  <div class="game-container">
    <div v-for="y in size" :key="y" class="game-row">
      <Switch v-for="(toggled, x) in grid[y-1]" :key="x"
              :isOn="toggled === true" @click="toggle(x,y-1)"/>
    </div>
  </div>
</template>

<script>
import Switch from '@/components/Switch.vue';

export default {
  name: 'Game',
  components: { Switch },
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
          row.push(Math.random() < rate);
        }

        return row;
      }

      function hasAnyOn(grid) {
        for (let y = 0; y < grid.length; y++) {
          for (let x = 0; x < grid.length; x++) {
            if (grid[y][x] === true) {
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
    toggle(x, y) {
      // toggle switch of clicked element and all adjacent ones
      this.toggleAt(x, y);
      this.toggleAt(x - 1, y);
      this.toggleAt(x + 1, y);
      this.toggleAt(x, y - 1);
      this.toggleAt(x, y + 1);
    },
    toggleAt(x, y) {
      if (y >= 0 && x >= 0 && y < this.size && x < this.size) {
        this.grid[y][x] = !this.grid[y][x];
      }
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
  }
}
</style>
