<template>
  <v-main>
    <nav-menu />
    <default-bar />
    <router-view />
  </v-main>
</template>

<script setup>
  //
import NavMenu from "@/layouts/default/NavMenu.vue";
  import DefaultBar from "@/layouts/default/AppBar.vue";
</script>
