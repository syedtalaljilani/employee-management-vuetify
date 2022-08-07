<template>
  <v-app>
    <v-content class="red">
       <Navbar/>
       <router-view/>
    </v-content>
    
  </v-app>
</template>

<script>
import Navbar from './components/NavBar.vue'
export default {
  components:{Navbar}
}
</script>

<style>
</style>