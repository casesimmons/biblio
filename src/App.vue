<template>
  <ul>
    <resource-item
      v-for="res in storedResources"
      :key="res.id"
      :title="res.title"
      :description="res.description"
      :link="res.link"
    ></resource-item>
  </ul>
</template>

<script>
import ResourceItem from './components/resource-items/ResourceItem.vue';

export default {
  components: {
    ResourceItem
  },
  data() {
    return {
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
  }
};
</script>
