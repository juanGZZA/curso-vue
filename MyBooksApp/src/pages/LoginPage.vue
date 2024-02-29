<script setup>
import{ ref } from "vue";

const emits = defineEmits(["hideLogin"]);

const email = ref();
const password = ref();

function login() {
  //toda la logica de autenticar usuario

  if (email.value === 'juan' && password.value === 'abc') {
    //Ingresa a la aplicacion
    emits("hideLogin");

  } else {
    //denegamos el acceso
    alert("Las credenciales son incorrectas")
  }
}

</script>

<template>
    <div class="login-container">
        <h1>Login</h1>
        <form @submit.prevent="login">
        <div>
            <label for="email">Email</label>
            <input v-model="email" type="text" name="email">
        </div>
        <div>
            <label for="password">Contraseña</label>
            <input v-model="password" type="text" name="password">
        </div>
        <button type="submit">Ingresar</button>
        </form>
    </div>

</template>

<style scoped>
/*Login*/
.login-container{
  width: 400px;
  margin: 50px auto;
  background-color: rgb(167, 199, 226);
  padding-block: 30px;
  border-radius: 30px;
}

.login-container > h1{
  text-align: center;
}

.login-container > form {
  display: block;
  padding: 20px;
}
</style>