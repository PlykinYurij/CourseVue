<template>
    <form @submit.prevent>
        <h4>Add post</h4>
        <input 
        v-model="post.title"
        class="input" 
        type="text" 
        placeholder="Title" 
        />
        <input 
        v-model="post.body"
        class="input" 
        type="text" 
        placeholder="Body" />
        <button class="btn" @click="createPost">Add</button>
    </form>
</template>

<script>
export default {
    data() {
        return {
            post: {
                title: '',
                body: '',
            }
        }
    },
    methods: {
        createPost() {
            this.post.id = Date.now();
            this.$emit('create', this.post)
            this.post={
                title: '',
                body: '',
            }
        }
    }
}

</script>

<style></style>