<template>
  <li>
    <div>
      <header>
        {{ title }}
        <button>X</button>
      </header>
    </div>
    <p>{{ description }}</p>
    <nav>
      <a :href="link">Visit</a>
    </nav>
  </li>
</template>

<script>
export default {
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

button {
  color: whitesmoke;
  border-style: none;
  font-size: 1rem;
}

button:hover,
button:active {
  color: red;
  border-style: none;
  font-size: 1rem;
  cursor: not-allowed;
}
</style>
