<template>
    <div id="formContainer">
        <form @submit="addPost">
            <div class="wrapper">
                <i @click="exitForm" class="fa-solid fa-x"></i>
                <div>
                    <label for="title">Title</label>
                    <input type="text" id="title" v-model="postData.title">
                </div>
                <div>
                    <label for="content">Content</label>
                    <textarea rows="20" type="text" id="content" v-model="postData.content"></textarea>
                    <button type="submit">Create</button>
                </div>

            </div>
        </form>
    </div>

</template>

<script>
import axios from 'axios';

export default {
    name: 'AddPost',
    data() {
        return {
            postData: {
                title: '',
                content: ''
            }
        };
    },
    methods: {
        addPost() {
            axios.post('http://localhost:3000/posts', this.postData)
                .then(response => console.log(response))
                .catch(error => console.log(error))
        },
        exitForm() {
            const el = document.getElementById('formContainer')
            el.style.display = 'none';
        }
    }
}
</script>

<style scoped>
#formContainer {
    display: none;
    z-index: 1;
    position: fixed;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
    border: 1px solid black;
    border-radius: 10%;
    width: 50%;
    max-height: 95vh;
    background-color: rgba(255, 255, 255, 0.8);
    -webkit-box-shadow: 0px 0px 5px 1px rgb(0, 0, 0);





}

form {
    display: flex;
    width: 100%;
    overflow: auto;
    margin: 20px;
}

.wrapper {
    display: flex;
    flex-direction: column;
    text-align: left;
    width: 100%;



}

.wrapper>div {
    display: flex;
    flex-direction: column;

    margin: 5px;
}

.wrapper>div>* {
    margin: 5px;
}

#title {
    width: 100%;
    padding: 10px;
    border: 2px solid black;

}

textarea {
    width: 100%;
    border: 2px solid black;
}

button {
    width: 80px;
    height: 40px;
    background-color: black;
    border-radius: 10%;
    color: white;
    opacity: 0.6;
}

i {
    text-align: right;
}

i:hover {
    color: red;
}
</style>