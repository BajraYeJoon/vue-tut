<!-- Slot Props -->

<template>
  <div>
    <h3 v-for="value in names" :key="value.name">
      <slot :name="name" :place="place"></slot>
    </h3>
  </div>
</template>

<script>
export default {
  name: "NameList",
  data() {
    return {
      names: [
        { name: "JOhn", place: "usa" },
        { name: "DOe", place: "uk" },
        { name: "Mary", place: "nep" },
      ],
    };
  },
};
</script>

<style lang="scss" scoped></style>
