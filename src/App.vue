<template>
    <div class="app">
        <post-form @create="createPost" />
        <post-list :posts="posts" />



    </div>
</template>

<script>
import PostList from './components/PostList.vue'
import PostForm from './components/PostForm.vue'
export default {
    components: {
        PostList, PostForm
    },
    data() {
        return {
            posts: [
                { id: 1, title: 'JavaScript', body: 'Discription post' },
                { id: 2, title: 'JavaScript 2', body: 'Discription post 2' },
                { id: 3, title: 'JavaScript 3', body: 'Discription post 3' },
            ],
            title: "",
            body: "",
        }
    },
    methods: {
        createPost(post) {
            this.posts.push(post)
        }
    }
}
</script>

<style>
* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}

.app {
    padding: 20px;
}

form {
    display: flex;
    flex-direction: column;
}

.input {
    width: 100%;
    border: 1px solid teal;
    padding: 10px 15px;
    margin-top: 15px;
}

.btn {
    align-self: flex-end;
    margin-top: 15px;
    padding: 10px 15px;
    background: none;
    color: teal;
    border: 1px solid teal
}
</style>