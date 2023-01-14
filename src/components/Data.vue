<template>
  <div>Composition - {{ c_firstName }}</div>
  <div>Mutated Comp - {{ newValue }}</div>
  <div>Reactive Comp - {{ info }}</div>
</template>

<script>
import { ref, reactive } from "vue";

export default {
  name: "DataComp",
  // entry point for ComAPI
  setup() {
    //returns a reactive and mutable value
    const c_firstName = ref("John");
    //to mutate the value
    c_firstName.value = "Doe";

    //store the value
    const newValue = `New Name is ${c_firstName.value}`;

    // reactive state
    const state = reactive({
      firstName: "Power",
      place: "usa",
      age: 45,
    });

    const info = `Hello ${state.firstName} ${state.place} ${state.age}`;

    return {
      c_firstName,
      newValue,
      info,
    };
  },
};
</script>

<style scoped></style>
