<template>
  <base-card>
    <base-button @click="setTab('stored-item')" :mode="storedResButtonMode"
      >My Resource</base-button
    >
    <base-button @click="setTab('add-resource')" :mode="addResButtonMode"
      >Add Resource</base-button
    >
  </base-card>
  <keep-alive>
    <component :is="selectedTab"></component>
  </keep-alive>
</template>

<script>
import StoredItem from './StoredItem';
import AddResource from './AddResource';

export default {
  provide() {
    return {
      resources: this.storedResources,
      addResource: this.addResource,
      deleteResource: this.removeResource
    };
  },
  components: {
    StoredItem,
    AddResource
  },
  data() {
    return {
      selectedTab: 'stored-item',
      storedResources: [
        {
          id: '124D',
          title: `Read The Fuckin' Manual`,
          description: 'The official Manual',
          link: 'https://youtube.com'
        },
        {
          id: '8121T',
          title: 'Read The Bread',
          description: 'The official Bread',
          link: 'https://google.com'
        }
      ]
    };
  },
  methods: {
    setTab(tab) {
      this.selectedTab = tab;
    },
    addResource(title, desc, link) {
      const newItem = {
        id: new Date().toISOString(),
        title,
        desc,
        link
      };
      this.storedResources.unshift(newItem);
      this.selectedTab = 'stored-item';
    },
    removeResource(key) {
      const resIndex = this.storedResources.findIndex(res => res.id === key);
      this.storedResources.splice(resIndex, 1);
    }
  },
  computed: {
    storedResButtonMode() {
      return this.selectedTab === 'stored-item' ? null : 'flat';
    },
    addResButtonMode() {
      return this.selectedTab === 'add-resource' ? null : 'flat';
    }
  }
};
</script>
