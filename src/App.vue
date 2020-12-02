<template>
  <the-header title="biblio"></the-header>
  <the-resources></the-resources>
</template>

<script>
import TheHeader from './components/layouts/TheHeader.vue';
import TheResources from './components/resource-items/TheResources.vue';

export default {
  components: {
    TheHeader,
    TheResources
  }
};
</script>

<style>
* {
  box-sizing: border-box;
  background-color: black;
}

html {
  font-family: Arial, Helvetica, sans-serif;
}

body {
  margin: 0;
}
</style>
