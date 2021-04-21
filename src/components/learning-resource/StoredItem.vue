<template>
  <ul>
    <resource-item
      v-for="item in resources"
      :key="item.id"
      :title="item.title"
      :description="item.description"
      :link="item.link"
    ></resource-item>
  </ul>
</template>

<script>
import ResourceItem from './ResourceItem';

export default {
  components: {
    ResourceItem
  },
  props: ['resources']
};
</script>

<style scoped>
ul {
  list-style: none;
  margin: 0;
  padding: 0;
  margin: auto;
  max-width: 40rem;
}
</style>
