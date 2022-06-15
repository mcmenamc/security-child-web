<template>

 
</template>

<script>
export default {
  name: "NavigationDrawerVue",
  data: () => ({
    drawer: true,
  }),
  computed: {
    showMenu() {
      return this.drawer || this.$vuetify.breakpoint.mdAndUp;
    },
  },
};
</script>

<style>
</style>