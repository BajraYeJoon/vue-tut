<template>
  <div>
    <!-- <DataComp /> -->
    <DemoTwo />
    <MethodComp />
  </div>
</template>

<script>
// import DemoOne from "@/components/Demo1.vue";
import DemoTwo from "@/components/DemoTwo.vue";
import MethodComp from "@/components/Methods.vue";
// import DataComp from '@/components/Data.vue';

export default {
  name: "CompApp",
  components: {
    // DemoOne,
    DemoTwo,
    MethodComp,
  },
};
</script>

<style lang="scss" scoped></style>
