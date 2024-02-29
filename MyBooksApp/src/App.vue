<script setup>
import { ref } from "vue"
import LoginPage from "./pages/LoginPage.vue"
import NavBar from "./components/NavBar.vue";



const isLoginShown = ref(true);

function changePage(page) {
  pageShown.value=page;
}



//navbar

const pageShown = ref("about-us");



</script>

<template>
  <!--login-->
  <LoginPage @hide-login="isLoginShown = false" v-if="isLoginShown === true"/>
  

  <!--Contenido de la app-->
  <div v-else>
    <!--navbar-->
    <NavBar @change-page="changePage" @hide-login="isLoginShown=true"/>
    <!--Pagina acerca de nosotros-->
    <!--Pagina de reseñas-->
    <!--Pagina de explorar-->
    

    <section class="about-us-container" v-if="pageShown === 'about-us'">
      <img src="https://www.esstudioediciones.com/blog/los-libros-en-espanol-mas-vendidos-de-la-historia.jpg" alt="">
      <h2>Acerca de nosotros</h2>
      <p>
        Lorem ipsum dolor, sit amet consectetur adipisicing elit. Aliquid veritatis possimus fugiat temporibus eius culpa labore, excepturi, natus nostrum molestias dolorem nihil tenetur exercitationem ipsa dolor voluptatum tempora. Modi sunt repudiandae quisquam doloremque assumenda corrupti eos voluptatum nemo, ad eius cum nostrum. Qui quibusdam numquam repellat ea. In ipsa impedit quidem corporis optio molestiae facilis doloribus labore commodi obcaecati. Ut corrupti sapiente optio ex a aliquam distinctio voluptas possimus velit? Dolores itaque cum temporibus quibusdam est quos facilis quam deserunt iure delectus atque ab, accusantium excepturi modi exercitationem dolore, eaque doloribus ea id necessitatibus. Voluptatem voluptatibus nostrum nam cumque temporibus harum exercitationem quibusdam a incidunt ea mollitia hic totam nihil, expedita ducimus veritatis cupiditate eaque natus sequi commodi, rem iste doloribus. Magnam impedit cumque earum, dignissimos culpa non necessitatibus recusandae voluptatibus, tempore ab veniam ea minus fugit illum vero et quibusdam dolore cupiditate expedita? Deserunt repudiandae accusamus maxime adipisci sint? 
      </p>
    </section>

    <section v-if="pageShown === 'explore'">
      <h2>Explorar</h2>
    </section>

    <section v-if="pageShown === 'reviews'">
      <h2>Reseñas</h2>
    </section>
  </div>

</template>

<style scoped>


/*Nav */
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

/* about us*/
.about-us-container{
  max-width: 700px;
  margin: auto;
}

.about-us-container > h2{
  text-align: center;
  font-weight: 600;
}

.about-us-container > img{
  width: 100%;
}
</style>
