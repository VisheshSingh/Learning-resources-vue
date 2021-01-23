<template>
  <div class="backdrop" @click.self="$emit('close')">
    <dialog open>
      <header>
        <h2>
          <slot name="header">{{ title }}</slot>
        </h2>
      </header>
      <section>
        <slot></slot>
      </section>
      <menu>
        <slot name="actions">
          <base-button @click="$emit('close')">Close</base-button>
        </slot>
      </menu>
    </dialog>
  </div>
</template>

<script>
export default {
  name: 'BaseDialog',
  props: ['title'],
  emits: ['close']
};
</script>

<style scoped>
.backdrop {
  position: fixed;
  top: 0;
  left: 0;
  width: 100vw;
  height: 100vh;
  background: rgba(0, 0, 0, 0.5);
  z-index: 10;
}

dialog {
  width: 40rem;
  position: fixed;
  top: 20vh;
  margin: auto;
  padding: 0;
  border-radius: 8px;
  background: #fff;
  box-shadow: 1px 3px 5px rgba(0, 0, 0, 0.25);
  z-index: 100;
}

header {
  background: #3a0062;
  color: #fff;
  width: 100%;
}

header h2 {
  margin: 0;
  padding: 10px;
}

section {
  padding: 1rem;
}

menu {
  padding: 1rem;
  margin: 0;
  display: flex;
  justify-content: flex-end;
}
</style>
