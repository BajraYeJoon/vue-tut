<template>
  <div>
    <h2>This is popip</h2>
    <input type="text " v-model="name" />
    <button @click="$emit('close', name)">Close popup</button>
  </div>
</template>

<script>
export default {
  name: "PopUp",
  emits: {
    close: (name) => {
      if (!name) {
        console.log("event validation failed");
        return false;
      } else {
        return true;
      }
    },
  },

  data() {
    return {
      name: "",
    };
  },
};
</script>

<style>
button {
  background-color: rgb(125, 77, 77);
}
</style>
