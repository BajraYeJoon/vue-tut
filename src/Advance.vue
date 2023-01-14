<template>
  <!-- <CardComp> Card content </CardComp>

  <CardComp>
    <h3>Card Content with heading</h3>
  </CardComp>

  <CardComp></CardComp>

  <CardComp>
    <template #header>
      <h3>Header</h3>
    </template>
    <template #default>
      <h3>Inside Content</h3>
    </template>
    <template #footer>
      <h3>Footer</h3>
      <button>This is button</button>
    </template>
  </CardComp> -->

  <NameList>
    <template v-slot:default="slotProps">
      {{ slotProps.name }} {{ slotProps.place }}
    </template>
  </NameList>
  <NameList>
    <template v-slot:default="slotProps">
      {{ slotProps.name }}
    </template>
  </NameList>
</template>

<script>
// import CardComp from "./components/Card.vue";
import NameList from "./components/NameList.vue";

export default {
  name: "AdvanceVue",
  components: {
    // CardComp,
    NameList,
  },
};
</script>

<style scoped>
button {
  border: 1px solid red;
}
</style>
