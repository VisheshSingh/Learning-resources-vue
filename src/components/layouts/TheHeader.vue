<template>
  <header>
    <h1>{{ title }}</h1>
  </header>
</template>

<script>
export default {
  name: 'TheHeader',
  props: ['title']
};
</script>

<style scoped>
header {
  width: 100%;
  background: #640032;
  display: flex;
  justify-content: center;
  align-items: center;
  height: 5rem;
}

header h1 {
  color: #fff;
  margin: 0;
}
</style>
