<template>
  <div>{{ firstName }}</div>
</template>

<script>
import { reactive, toRefs } from "vue";
export default {
  name: "DemoTwo",
  setup() {
    const state = reactive({
      firstName: "jOHN",
    });

    setTimeout(() => {
      state.firstName = "Doe";
    }, 2000);

    return toRefs(state);
  },
};
</script>

<style lang="scss" scoped></style>
