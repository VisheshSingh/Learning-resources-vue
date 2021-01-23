<template>
  <div>
    <slot></slot>
  </div>
</template>

<script>
export default {
  name: 'BaseCard'
};
</script>

<style scoped>
div {
  border: 1px solid #ccc;
  border-radius: 8px;
  box-shadow: 1px 3px 5px rgba(0, 0, 0, 0.2);
  margin: 20px auto;
  padding: 20px;
  max-width: 40rem;
}
</style>
