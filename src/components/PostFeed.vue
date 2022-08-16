<template>
    <div class="container">



        <div v-for="post of posts" :key="post.id" class="blog-post">
            <i @click="deletePost(post.id)" class="fa-solid fa-x"></i>
            <h1>{{ post.title }}</h1>
            <p>{{ post.content }}</p>

        </div>



    </div>
</template>




<script>
import axios from 'axios';

export default {
    name: 'PostFeed',
    data() {
        return {
            posts: []
        };
    },
    async created() {
        try {
            const res = await axios.get('http://localhost:3000/posts');
            this.posts = res.data;
        } catch (e) {
            console.error(e);
        }
    },
    methods: {
        deletePost(id) {
            axios.delete(`http://localhost:3000/posts/${id}`)
                .then(response => console.log(response))
                .catch(error => console.log(error));
            this.posts = this.posts.filter((post) => post.id !== id)
        }
    }

}
</script>

<style>
.container {
    display: flex;
    flex-direction: column;
    align-items: center;
    background-color: #f8f8e9;
    justify-content: center;
    width: 100%;
    min-height: 100vh;
    padding-top: 80px;
}

.blog-post>i {
    float: right;
}

.blog-post {
    padding: 50px;
    margin: 15px;
    text-align: left;
    border-left: 2px solid gray;
    width: 40%;
}
</style>