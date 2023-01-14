<template>
  <div>
    <input
      type="text"
      :value="inputValue"
      @input="$emit('update:inputValue', $event.target.value)"
    />
  </div>
</template>

<script>
export default {
  name: "InputELement",
  props: {
    inputValue: String,
  },
};
</script>

<style scoped></style>
