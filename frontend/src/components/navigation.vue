<template>
    <nav class="navBar">
        <router-link to="/" class="btn">
            На початкову сторінку
        </router-link>
        <router-link to="/about" class="btn">
            Про авторів
        </router-link>

        <router-link to="/create" class="btn">
            Створити нове запитання
        </router-link>
    </nav>
</template>
<script>
export default {
    name: "NavigationPanel"
}
</script>
<style>
.navBar{
    margin-left: 300px;
}
</style>