<template>
  <div>
    <!-- * Barra de navegación -->
    <v-navigation-drawer
      width="300"
      app
      color="white"
      temporary
      touchless
      v-model="drawer"
    >
      <!-- <v-list dense>
        <v-list-item>
          <v-list-item-title class="d-flex justify-center align-center">
            <span class="">Bienvenido </span>
            <v-spacer></v-spacer>
            <v-btn icon @click.stop="drawer = !drawer">
              <v-icon>fas fa-times</v-icon>
            </v-btn>
          </v-list-item-title>
        </v-list-item>
        <v-divider class=""></v-divider>
      </v-list> -->
      <v-img height="180" class="" src="@/assets/images/like.png">
        <v-row class="mx-1 my-0" align-content="end" style="height: 100%">
          <v-col cols="12" class="py-0">
            <span class="white--text text-caption">CODEA APP</span>
          </v-col>
          <v-col cols="12" class="py-0">
            <span class="white--text text-caption">informes@gmail.com</span>
          </v-col>
        </v-row>
      </v-img>
      <v-list dense>
        <v-list-item-group v-model="selectedList" color="primary">
          <v-list-item v-for="item in list" :key="item.id" class="pb-2">
            <v-list-item-content @click="$router.push({ path: item.path })">
              <v-list-item-title v-text="item.text"></v-list-item-title>
            </v-list-item-content>
          </v-list-item>
        </v-list-item-group>
      </v-list>
    </v-navigation-drawer>
    <!-- * Barra de navegación -->

    <!-- * Barra de navegación lateral -->
    <v-app-bar elevation="0" color="secondary" height="70" app dark>
      <v-btn icon class="mx-4" @click="toggleDrawer">
        <v-icon>fas fa-bars</v-icon>
      </v-btn>
      <v-toolbar-title>
        <span class="font-weight-bold">{{ $route.meta.title }}</span>
      </v-toolbar-title>
    </v-app-bar>
  </div>
</template>

<script>
import Navigation from "@/components/layouts/Navigation";
export default {
  name: "AppBar",
  components: {
    Navigation,
  },
  data: () => ({
    drawer: false,
    selectedList: 0,
    list: [
      {
        text: "Perfil",
        path: "/",
      },
      {
        text: "Camara",
        path: "/camera",
      },
      {
        text: "Comando por voz",
        path: "/command-voice",
      },
      {
        text: "Alertas",
        path: "/alerts",
      },
      {
        text: "Ubicacion",
        path: "/location",
      },
    ],
  }),
  methods: {
    toggleDrawer() {
      this.drawer = !this.drawer;
    },
  },
  computed: {
    showMenu() {
      return this.drawer || this.$vuetify.breakpoint.mdAndUp;
    },
  },
};
</script>

<style>
</style>