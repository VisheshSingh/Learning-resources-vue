<template>
  <button :type="type" :class="mode">
    <slot></slot>
  </button>
</template>

<script>
export default {
  name: 'BaseButton',
  props: ['type', 'mode']
};
</script>

<style scoped>
button {
  background: #3a0062;
  color: #fff;
  padding: 10px 20px;
  border-radius: 1rem;
  border: 0;
  cursor: pointer;
}

button:hover,
button:active {
  background: #270041;
}

.flat {
  background: transparent;
  color: #3a0062;
  border: none;
}

.flat:hover,
.flat:active {
  background: #edd2ff;
}
</style>
