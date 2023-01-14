<template>
    <div>
        <CreatPost />
        <PostList />

    </div>
</template>

<script>
import CreatPost from "./components/Http/CreatPost.vue";
import PostList from "./components/Http/PostList.vue";


export default {
    name: "HttpCall",
    components: {
        PostList,
        CreatPost
    },
};
</script>

<style lang="scss" scoped>

</style>
