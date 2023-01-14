<template>
  <div>
    <button @click="active = 'TabA'">Tab A</button>
    <button @click="active = 'TabB'">Tab B</button>

    <button @click="active = 'TabC'">Tab C</button>
  </div>
  <!-- 
  <div class="content-container">
    <TabA v-if="active === 'TabA'" />
    <TabB v-if="active === 'TabB'" />
    <TabC v-if="active === 'TabC'" />
  </div> -->

  <!-- component is special tag that makes the dynamic component possible -->
  <!-- keeping the value persist -->
  <keep-alive>
    <component :is="active" class="content-container" />
  </keep-alive>
</template>

<script>
import TabA from "./components/Tabs/TabA.vue";
import TabB from "./components/Tabs/TabB.vue";

import TabC from "./components/Tabs/TabC.vue";

export default {
  name: "DynamicComp",

  components: { TabA, TabB, TabC },

  data() {
    return {
      active: "TabA",
    };
  },
};
</script>

<style scoped>
.content-container {
  width: 300px;
  height: 300px;
  border: 1px solid red;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
}
</style>
