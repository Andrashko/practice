<template>
    <nav>
        <router-link to="/" class="st">
            На початкову сторінку
        </router-link>
        <router-link to="/about" class="st">
            Про авторів
        </router-link>

        <router-link to="/create" class="st">
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
.st{
   
  text-decoration: none;
  display: inline-block;
  padding: 12px 40px;
  margin: 10px 20px;
  border-radius: 30px;
  background-image: linear-gradient(45deg, #6ab1d7 0%, #33d9de 50%, #002878 100%);
  background-position: 100% 0;
  background-size: 200% 200%;
  font-family: 'Montserrat', sans-serif;
  font-size: 24px;
  font-weight: 300;
  color: white;
  box-shadow: 0 16px 32px 0 rgba(0, 40, 120, .35);
  transition: .5s;
}
.st:hover {
  box-shadow: 0 0 0 0 rgba(0, 40, 120, 0);
  background-position: 0 0;
}

</style>