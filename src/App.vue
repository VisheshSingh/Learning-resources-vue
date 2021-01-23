<template>
  <the-header title="RememberMe"></the-header>
  <the-resource></the-resource>
</template>

<script>
import TheHeader from './components/layouts/TheHeader.vue';
import TheResource from './components/learning-resources/TheResource';

export default {
  name: 'App',
  components: {
    TheHeader,
    TheResource
  }
};
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Manrope:wght@200;400;700&display=swap');

* {
  box-sizing: border-box;
}

html {
  font-family: 'Manrope', sans-serif;
}

body {
  margin: 0;
}
</style>
