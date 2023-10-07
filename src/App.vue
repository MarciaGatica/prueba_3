<script setup>
import { RouterLink, RouterView } from 'vue-router'


</script>

<template>
  <div class="cabeza">

      <nav class="navbar">
        <img alt="Vue logo" class="logo" src="@/assets/logo_ufro.png"/>
    
    <div class="btn-group">
      <a  href="#" class="btn btn-primary active">
        <RouterLink to="/noticias" style="text-decoration: none">Noticias</RouterLink>
      </a>
      <a href="#" class="btn btn-primary">
        <RouterLink to="/eventos" style="text-decoration: none">Eventos</RouterLink>
      </a>
    </div>
    </nav>
  </div>


  <div>
    <RouterView />
  </div>
</template>

<style scoped>
.logo{
  height:60 ;
}

.btn-group {
  margin-right: 5%;

}

.btn{
  
 background-color: aliceblue;
 
}

.navbar {
  background-color: #003A6C;
}

</style>
