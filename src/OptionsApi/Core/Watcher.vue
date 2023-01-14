<template>
  <h3>Volume (0-20)</h3>
  <h4>Current Volume {{ volume }}</h4>
  <button @click="volume += 2">increase</button>
  <button @click="decreaseVolume">decrease</button>

  <!-- immediate and deep watcher -->
  <input type="text" v-model="movie" />
  <input type="text" v-model="movieInfo.title" />

  <input type="text" v-model="movieInfo.actor" />
</template>

<script>
export default {
  name: "WatcherVue",
  data() {
    return {
      volume: 0,
      maxValue: 16,
      movie: "avatar",
      movieInfo: {
        title: "",
        actor: "",
      },
    };
  },

  methods: {
    decreaseVolume() {
      if (this.volume <= 0) {
        this.volume = 0;
      } else {
        this.volume -= 2;
      }
    },
  },

  watch: {
    volume(newValue, oldValue) {
      if (newValue > oldValue && newValue === this.maxValue) {
        alert("max value reached");
      }
    },

    movie: {
      handler(newValue) {
        console.log(`api called with ${newValue}`);
      },
      immediate: true,
    },

    movieInfo: {
      handler(newValue) {
        console.log(`api called with ${newValue.title} and ${newValue.actor}`);
      },
      deep: true,
    },
  },
};
</script>

<style lang="scss" scoped></style>
