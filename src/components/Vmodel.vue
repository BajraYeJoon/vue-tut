<template>
  <!-- <div>
    options api -->
  <!-- <input type="text" placeholder="name" v-model="info.name" ref="inputref" />
  </div> -->

  <!-- composiiton api -->
  <input type="text" placeholder="name" v-model="ref_name" ref="inputref" />
  <input
    type="text"
    placeholder="name"
    v-model="reactive_name"
    ref="inputref"
  />
  <hr />

  <!-- composition api & computed  -->
  <input type="number" placeholder="age" v-model.number.lazy="ref_age" />
  <h4>the age is {{ getAge }}</h4>

  <input
    type="number"
    placeholder="reactive_age"
    v-model.number="reactive_age"
  />
  <h4>the age is {{ reactivegetAge }}</h4>
</template>

<script>
import { ref, reactive, toRefs, computed } from "vue";

export default {
  name: "VModel",
  setup() {
    const ref_name = ref("");

    const ref_age = ref("");
    const state = reactive({
      reactive_name: "",
      reactive_age: "",
    });

    const getAge = computed(() => {
      return `${ref_age.value}`;
    });

    const reactivegetAge = computed(() => {
      return `${state.reactive_age}`;
    });

    return {
      ref_name,
      getAge,
      ref_age,
      reactivegetAge,
      ...toRefs(state),
    };
  },

  //   data() {
  //     return {
  //       info: {
  //         name: "",
  //       },
  //     };
  //   },
  //   //access the DOM
  //   mounted() {
  //     this.$refs.inputref.focus();
  //   },
};
</script>

<style lang="scss" scoped></style>
