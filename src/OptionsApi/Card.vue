<template>
  <div class="card">
    <!-- anything written inside the slot will be replaced by the content that the parent provides whtn the component is viewed -->
    <div id="card-header">
      <slot name="header"></slot>
    </div>
    <div id="card-content">
      <slot></slot>
    </div>
    <div id="card-footer">
      <slot name="footer"></slot>
    </div>
  </div>
</template>

<script>
export default {
  name: "CardComp",
};
</script>

<style>
.card {
  box-shadow: 0 4px 8px 0 rgba(0, 0, 0, 0.3);
  transition: 0.3s;
  padding: 16px;
  margin-bottom: 20px;
  width: 200px;
}

.card:hover {
  box-shadow: 0 8px 16px 0 rgba(0, 0, 0, 0.2);
}
</style>
