<template>
  <li>
    <base-card>
      <header>
        <nav>
          <a :href="link">{{ title }}</a>
        </nav>
        <base-button>X</base-button>
      </header>
      <p>{{ description }}</p>
    </base-card>
  </li>
</template>

<script>
import BaseButton from '../UI/BaseButton.vue';

export default {
  components: {
    BaseButton
  },
  props: ['title', 'description', 'link']
};
</script>

<style scoped>
li {
  margin: auto;
  max-width: 40rem;
  color: whitesmoke;
  list-style-type: '📍 ';
  margin-bottom: 15px;
  font-size: 1rem;
}

header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  font-size: 1.5rem;
}

p {
  font-size: 1rem;
  margin: 0.5rem 0;
  line-height: 1.5rem;
  color: whitesmoke;
}

a {
  text-decoration: none;
  color: whitesmoke;
}

a:hover,
a:active {
  color: green;
}
</style>
