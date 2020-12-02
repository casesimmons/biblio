<template>
  <base-card>
    <base-button
      @click="setSelectedTab('stored-resources')"
      :mode="storedResButtonMode"
      >Archived</base-button
    >
    <base-button
      @click="setSelectedTab('add-resource')"
      :mode="addResButtonMode"
      >Add</base-button
    >
  </base-card>
  <keep-alive>
    <component :is="selectedTab" />
  </keep-alive>
</template>

<script>
import StoredResources from './StoredResources.vue';
import AddResource from './AddResource.vue';
export default {
  components: {
    StoredResources,
    AddResource
  },
  data() {
    return {
      selectedTab: 'saved-resources',
      storedResources: [
        {
          id: 'sea-ranch',
          title: 'Sea Ranch, California',
          description:
            'The Sea Ranch is a planned unincorporated community and census-designated place (CDP) located in Sonoma County, California',
          link: 'https://en.wikipedia.org/wiki/Sea_Ranch,_California'
        },
        {
          id: 'discogs-data',
          title: 'Discogs Data API',
          description:
            'Here you will find monthly dumps of Discogs Release, Artist, Label, and Master Release data.  The data is in XML format and formatted according to the API spec: http://www.discogs.com/developers/',
          link: 'https://data.discogs.com/'
        },
        {
          id: 'generative-artistry',
          title: 'Generative Artistry',
          description:
            'A range of interactive tutorials, exploring ideas and techniques used in generative art.',
          link: 'https://generativeartistry.com/'
        }
      ]
    };
  },
  provide() {
    return {
      resources: this.storedResources,
      addResource: this.addResource,
      removeResource: this.removeResource
    };
  },
  computed: {
    storedResButtonMode() {
      return this.selectedTab === 'stored-resources' ? null : 'flat';
    },
    addResButtonMode() {
      return this.selectedTab === 'add-resource' ? null : 'flat';
    }
  },
  methods: {
    setSelectedTab(tab) {
      this.selectedTab = tab;
    },
    addResource(title, description, url) {
      const newResource = {
        id: new Date().toISOString(),
        title: title,
        description: description,
        link: url
      };
      // add new entry to top of stored resources
      this.storedResources.unshift(newResource);
      // change to stored-resources tab
      this.selectedTab = 'stored-resources';
    },
    removeResource(resId) {
      const resIndex = this.storedResources.findIndex(res => res.id === resId);
      this.storedResources.splice(resIndex, 1);
    }
  }
};
</script>
