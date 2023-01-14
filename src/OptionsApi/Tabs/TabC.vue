<template>
  <!-- making dynamic components as vue create new instances everytime rendering happens -->
  <div>
    TAB-C Content
    <input type="text" v-model="name" />
  </div>
</template>

<script>
export default {
  name: "TabC",
  data() {
    return {
      name: " ",
    };
  },
};
</script>

<style lang="scss" scoped></style>
