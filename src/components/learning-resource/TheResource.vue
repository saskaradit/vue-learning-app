<template>
  <base-card>
    <base-button @click="setTab('stored-resources')">My Resource</base-button>
    <base-button @click="setTab('add-resource')">Add Resource</base-button>
  </base-card>
  <component :is="selectedTab"></component>
</template>

<script>
import StoredItem from './StoredItem';
import AddResource from './AddResource';

export default {
  component: {
    StoredItem,
    AddResource
  },
  data() {
    return {
      selectedTab: 'stored-resources'
    };
  },
  methods: {
    setTab(tab) {
      this.selectedTab = tab;
    }
  }
};
</script>
