<template>
  <h1 v-if="num === 0">The number is zero</h1>
  <h1 v-else-if="num < 0">The num is -</h1>
  <h1 v-else>The number is not zero</h1>

  <!-- It acts similar to React Fragment -->
  <!-- v-if gets removed from the DOM -->
  <template v-if="display">
    <h3>John</h3>
    <h4>Nepal</h4>
  </template>

  <!-- v-show // hide or show the element
   it persists in the DOM and can be used in toggle
-->
  <h4 v-show="showValue">V-show</h4>

  <!-- List rendering7 -->
  <span>list rendering using v-for</span>
  <hr />
  <h5 v-for="(name, index) in names" :key="name">{{ index }} {{ name }}</h5>

  <!-- array of objects -->
  <span>list rendering (array of object) using v-for</span>
  <hr />
  <h5 v-for="name in fullNames" :key="name">
    {{ name.first }} {{ name.last }}
  </h5>
</template>

<script>
export default {
  name: "MoreVue",
  data() {
    return {
      num: -2,
      display: true,
      showValue: true,

      names: ["john", "bruce", "evan"],

      fullNames: [
        {
          first: "John",
          last: "Doe",
        },
        {
          first: "Bruce",
          last: "Almighty",
        },
        {
          first: "Evan ",
          last: "Power",
        },
      ],
    };
  },
};
</script>

<style></style>
