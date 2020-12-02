<template>
  <base-card>
    <base-button @click="setSelectedTab('stored-resources')"
      >Archived</base-button
    >
    <base-button @click="setSelectedTab('add-resource')">Add</base-button>
  </base-card>
  <component :is="selectedTab"></component>
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
      resources: this.storedResources
    };
  },
  methods: {
    setSelectedTab(tab) {
      this.selectedTab = tab;
    }
  }
};
</script>
