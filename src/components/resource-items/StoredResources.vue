<template>
  <!-- <base-button @click="loadResources">Load</base-button> -->
  <p v-if="isLoading">Loading...</p>
  <ul v-if="!isLoading">
    <resource-item
      v-for="res in resources"
      :key="res.id"
      :id="res.id"
      :title="res.title"
      :description="res.description"
      :link="res.link"
    ></resource-item>
  </ul>
</template>

<script>
import ResourceItem from './ResourceItem.vue';

export default {
  components: {
    ResourceItem
  },
  data() {
    return {
      resources: [],
      isLoading: false
    };
  },
  provide() {
    return {
      removeResource: this.removeResource,
      loadResources: this.loadResources
    };
  },
  methods: {
    loadResources() {
      this.isLoading = true;
      fetch('https://biblio-37450.firebaseio.com/resources.json')
        .then(response => {
          if (response.ok) {
            return response.json();
          }
        })
        .then(data => {
          this.isLoading = false;
          const results = [];
          for (const id in data) {
            results.push({
              id: id,
              title: data[id].title,
              description: data[id].description,
              link: data[id].link
            });
            this.resources = results;
          }
        });
    },
    removeResource(resId) {
      console.log(resId);
      fetch(`https://biblio-37450.firebaseio.com/resources/${resId}.json`, {
        method: 'DELETE'
      })
        .then(response => response.json())
        .then(() => this.loadResources());
    }
  },
  mounted() {
    this.loadResources();
  }
};
</script>

<style scoped>
p {
  color: whitesmoke;
  margin: 0;
  padding: 0;
  margin: auto;
  max-width: 40rem;
  display: flex;
  justify-content: center;
}

ul {
  margin: 0;
  padding: 0;
  margin: auto;
  max-width: 40rem;
}
</style>
