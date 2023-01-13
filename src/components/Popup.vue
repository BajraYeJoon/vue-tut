<template>
  <div>
    <h2>This is popip</h2>
    <button @click="$emit('close', 'John')">Close popup</button>
  </div>
</template>

<script>
export default {
  name: "PopUp",
  emits: ["close"],
};
</script>

<style lang="scss" scoped></style>
