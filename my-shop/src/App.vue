<script setup>
import { RouterLink, RouterView } from 'vue-router';
</script>

<template>
  <v-toolbar color="green">
    <v-tab to="/">Home</v-tab>
    <v-tab to="/about">About</v-tab>
    <v-tab to="/services">Services</v-tab>
    <v-tab to="/">Contacts</v-tab>
    <v-tab to="/">Login</v-tab>
    <v-tab to="/signup">Signup</v-tab>
  </v-toolbar>
  <RouterView/>
</template>

<style scoped>

</style>
