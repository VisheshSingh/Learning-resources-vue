<template>
  <base-card>
    <form @submit.prevent="handleSubmit">
      <div class="form-control">
        <label for="title">Title</label>
        <input type="text" name="title" id="title" v-model="title" />
      </div>
      <div class="form-control">
        <label for="description">Description</label>
        <textarea
          id="description"
          name="description"
          rows="3"
          v-model="description"
        ></textarea>
      </div>
      <div class="form-control">
        <label for="resource">Resource</label>
        <input type="url" name="resource" id="resource" v-model="resource" />
      </div>
      <base-button type="submit">Add resource</base-button>
    </form>
    <teleport to="body">
      <base-dialog
        title="Form submission error"
        v-if="inputIsInvalid"
        @close="inputIsInvalid = false"
      >
        <template #default><p>Please check all inputs</p></template>
        <template #actions
          ><base-button @click="inputIsInvalid = false"
            >ok</base-button
          ></template
        >
      </base-dialog>
    </teleport>
  </base-card>
</template>

<script>
export default {
  inject: ['addNewResource'],
  name: 'AddResource',
  data() {
    return {
      title: '',
      description: '',
      resource: '',
      inputIsInvalid: false
    };
  },
  computed: {
    formIsInvalid() {
      return !this.title || !this.description || !this.resource;
    }
  },
  methods: {
    handleSubmit() {
      if (
        this.title.trim() === '' ||
        this.description.trim() === '' ||
        this.resource.trim() === ''
      ) {
        this.inputIsInvalid = true;
        return;
      }
      this.addNewResource({
        title: this.title,
        description: this.description,
        resource: this.resource
      });
      this.title = '';
      this.description = '';
      this.resource = '';
    }
  }
};
</script>

<style scoped>
label {
  font-weight: bold;
  display: block;
  margin-bottom: 0.5rem;
}
input,
textarea {
  display: block;
  width: 100%;
  font: inherit;
  padding: 0.15rem;
  border: 1px solid #ccc;
}
input:focus {
  outline: none;
  border-color: #3a0061;
  background-color: #f7ebff;
}
.form-control {
  margin: 1rem 0;
}
</style>
