<template>
  <stored-resource :resources="storedResources"></stored-resource>
</template>

<script>
import StoredResource from './components/learning-resources/StoredResource';

export default {
  name: 'App',
  components: {
    StoredResource
  },
  data() {
    return {
      storedResources: [
        {
          id: 1,
          title: 'Google',
          description: 'Learn to google stuff..',
          link: 'https://google.com'
        },
        {
          id: 2,
          title: 'Vue.js',
          description: 'A Progressive framework for building UIs',
          link: 'https://vue.org'
        }
      ]
    };
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
