<template>
  <div>
    hello

    <h1 v-bind="$attrs">{{ title }}</h1>
    <p>Likes = {{ likes }}</p>
    <span>Published{{ isPublished ? "Yes" : "No" }}</span>
  </div>
</template>

<script>
export default {
  name: "ArticleComp",
  props: {
    title: {
      type: String,
      required: true,
      default: "Default title",
    },
    likes: Number,
    isPublished: Boolean,
  },
  inheritAttrs: false,
};
</script>

<style scoped></style>
