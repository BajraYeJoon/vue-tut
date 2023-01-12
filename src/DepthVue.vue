<template>
  <div>
    <h2>add - {{ add(8, 10, 15) }}</h2>
    <h2>{{ name }}</h2>
    <button v-on:click="changeName($event), inc(1, $event)">changename</button>

    <h3>{{ count }}</h3>
    <button v-on:click="inc(2)">increment by 2</button>

    <button v-on:click="inc(5)">increment by 5</button>

    <button @click="inc(8, $event)">increment by 8</button>
  </div>
</template>

<script>
export default {
  name: "DepthVue",
  data() {
    return {
      name: "john",
      count: 0,
    };
  },

  //logic that can be reused
  methods: {
    add(a, b, c) {
      return a + b + c;
    },

    inc(num, event) {
      this.count += num;
      console.log(event);
    },

    changeName(event) {
      this.name = "doe";
      console.log(event);
    },
  },
};
</script>

<style></style>
