<template>
    <div>
        <form @submit.prevent="onSubmit">
            <div>
                <label for="userId">Post User Id</label>
                <input type="number" v-model.number="formData.userId" ref="inputRef">
            </div>
            <div>
                <label for="title">Post Title</label>
                <input type="text" v-model="formData.title">
            </div>
            <div>
                <label for="body">Post Body</label>
                <input type="text" v-model="formData.body">
            </div>
            <button type="submit">Create Post</button>
        </form>
    </div>
</template>

<script>
import axios from 'axios';

export default {
    name: 'CreatePost',
    //accessing the DOM
    mounted() {
        this.$refs.inputRef.focus()
    },

    data() {

        return {
            formData: {
                userId: '',

                title: '',
                body: ''
            }
        }
    },
    methods: {
        onSubmit() {
            axios.post('https://jsonplaceholder.typicode.com/posts', this.formData)
                .then(response => {
                    console.log(response.data)


                }
                )
                .catch(err => console.log(err))

        }
    },

}
</script>

<style lang="scss" scoped>

</style>