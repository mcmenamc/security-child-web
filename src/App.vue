<template>
  <v-app>
    <AppBar/>
    <v-main>
      <v-container fluid>
        <router-view/>
      </v-container>
    </v-main>
    <Footer/>
  </v-app>
</template>

<script>
import AppBar from '@/components/layouts/AppBar';
import Footer from '@/components/layouts/Footer';
export default {
  name: 'App',
  components: {
    AppBar,
    Footer
  },
  data: () => ({
    name: 'Home',
  }),

};
</script>
<style>
@font-face {
  font-family: 'Indie Flower';
  src: local('Indie Flower'), url('./assets/fonts/IndieFlower-Regular.ttf') format('truetype');
}


</style>