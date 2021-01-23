<template>
  <base-card>
    <base-button
      @click="setSelectedTab('stored-resource')"
      :mode="storedResBtnMode"
      >Stored Resources</base-button
    >
    <base-button @click="setSelectedTab('add-resource')" :mode="addResBtnMode"
      >Add Resource</base-button
    >
  </base-card>
  <component :is="selectedTab"></component>
</template>

<script>
import StoredResource from './StoredResource';
import AddResource from './AddResource';

export default {
  name: 'TheResource',
  components: {
    StoredResource,
    AddResource
  },
  data() {
    return {
      selectedTab: 'stored-resource',
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
  },
  provide() {
    return {
      resources: this.storedResources
    };
  },
  computed: {
    storedResBtnMode() {
      return this.selectedTab === 'stored-resource' ? null : 'flat';
    },
    addResBtnMode() {
      return this.selectedTab === 'add-resource' ? null : 'flat';
    }
  },
  methods: {
    setSelectedTab(tab) {
      this.selectedTab = tab;
    }
  }
};
</script>

<style></style>
