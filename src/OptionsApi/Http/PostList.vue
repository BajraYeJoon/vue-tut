<template>
    <div>
        <!-- <button @click="getPosts">Load Post</button> -->
        <h2 v-if="loading">Loading...</h2>
        <div v-for="post in posts" :key="post.id">
            <h3>{{ post.id }} {{ post.title }}</h3>
            <p>{{ post.body }}</p>
        </div>
    </div>
</template>

<script>
import axios from "axios";

export default {
    name: "PostList",
    // on page load the UI is populated!!!
    created() {
        this.getPosts()
    },
    data() {
        return {
            posts: [],
            loading: false

        };
    },

    methods: {
        getPosts() {
            this.loading = true
            axios
                .get("https://jsonplaceholder.typicode.com/posts")
                .then((res) => {
                    console.log(res.data);

                    this.posts = res.data;
                    this.loading = false
                })

                .catch((err) => console.log(err));
        },
    },
};
</script>

<style lang="scss" scoped>

</style>
