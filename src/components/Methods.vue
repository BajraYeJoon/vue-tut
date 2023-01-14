<template>
  <h2>{{ name }}</h2>
  <button @click="setName">Change Name</button>

  <h2>{{ c_name }}</h2>
  <button @click="changeName">Change Name</button>
</template>

<script>
import { reactive, toRefs } from "vue";
export default {
  name: "MethodComp",
  setup() {
    // let c_name = ref("John");
    const state = reactive({
      c_name: "John",
    });

    function changeName() {
      state.c_name = "Doe";
    }

    return {
      //   c_name,
      ...toRefs(state),
      changeName,
    };
  },

  data() {
    return {
      name: "John",
    };
  },
  methods: {
    setName() {
      this.name = "Doe";
    },
  },
};
</script>

<style lang="scss" scoped></style>
