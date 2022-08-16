<template>
    <div id="topContainer">

        <h1 style="margin-left: 10px;">Blogblog</h1>

    </div>
    <div id="leftContainer">
        <i @click="toggleForm" class="fa-solid fa-plus fa-xl"></i>
    </div>
</template>

<script>
export default {
    name: 'NavBar',
    methods: {
        toggleForm() {
            const el = document.getElementById("formContainer");
            el.style.display = 'flex';

        }
    }
}
</script>

<style scoped>
#topContainer {
    background-color: white;
    display: flex;
    align-items: center;
    color: red;
    text-shadow: 2px;
    height: 80px;
    width: 100%;
    position: fixed;
    box-shadow: 2px 2px 12px 0px rgb(170, 171, 175);

}

#leftContainer {
    float: left;
    position: fixed;
    background-color: #f8f8e9;
    height: 20vh;
    margin-top: 90px;
    padding: 20px;

}

i {
    transition: all .2s ease-in;
}

i:hover {

    transform: scale(2.0);
}
</style>