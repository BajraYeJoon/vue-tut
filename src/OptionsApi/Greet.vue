<template>
  <div>Hello {{ name }} {{ place }}</div>
</template>

<script>
export default {
  name: "GreetVue",
  props: ["name", "place"],
};
</script>

<style></style>
