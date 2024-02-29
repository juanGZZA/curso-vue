<script setup>

const emits = defineEmits(["changePage", "hideLogin"]);


</script>


<template>
    <nav>
      <h2>MyBooksApp</h2>
      <div>
        <span @click="emits('changePage', 'about-us')">Acerca de nosotros</span>
        <span @click="emits('changePage', 'explore')">Exploar</span>
        <span @click="emits('changePage', 'reviews')">Reseñas</span>
        <span @click="emits('hideLogin')">Cerrar sesión</span>
      </div>
    </nav>

</template>


<style scoped>
nav{
  display: flex;
  align-items: center;
  justify-content: space-between;
  background-color: gainsboro;
  width: 100%;
}

nav > div > span{
  margin-right: 20px;
} 
</style>