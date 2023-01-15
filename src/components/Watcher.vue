<template>
  <div>
    <input type="text" v-model="name" />
    <input type="text" v-model="place" />

    <input type="text" v-model="re_name" />
    <input type="text" v-model="re_place" />
  </div>
</template>

<script>
import { ref, watch, reactive, toRefs } from "vue";

export default {
  name: "WatchVue",
  setup() {
    const name = ref("");
    const place = ref("adf");

    const state = reactive({
      re_name: " ",
      re_place: "",
    });

    // for reactive we have to use an arrow function to make the data to be consolled
    watch(
      () => {
        return { ...state };
      },
      (newValues, oldValues) => {
        console.log("name old", oldValues.re_name);
        console.log("name new", newValues.re_place);

        console.log("place old", oldValues.re_name);
        console.log("place new", newValues.re_place);
      }
    );

    // in refs we can pass a single value or array in case of multiple source and access it using the indexes of the refs declared
    watch(
      [name, place],
      (newValues, oldValues) => {
        console.log("name old", oldValues[0]);
        console.log("name new", newValues[0]);

        console.log("place old", oldValues[1]);
        console.log("place new", newValues[1]);
      },
      {
        immediate: true,
      }
    );

    return { name, place, ...toRefs(state) };
  },
};
</script>

<style lang="scss" scoped></style>
