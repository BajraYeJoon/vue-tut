<template>
  <p>{{ char }}/20</p>
  <input type="text" v-model="text" @input="updateLength" maxlength="20" />
</template>

<script>
export default {
  name: "CharVue",
  data() {
    return {
      text: "",
      char: 0,
    };
  },
  methods: {
    updateLength() {
      this.char = this.text.length;
    },
  },
};
</script>
