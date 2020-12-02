<template>
  <button :type="type" :class="mode">
    <slot></slot>
  </button>
</template>

<script>
export default {
  props: ['type', 'mode']
};
</script>

<style scoped>
button {
  color: whitesmoke;
  border-style: none;
  background-color: transparent;
  outline: none;
  font-size: 1rem;
}

button:hover,
button:active {
  color: rgb(0, 91, 70);
  border-style: none;
  outline: none;
  font-size: 1rem;
  cursor: pointer;
}

.flat {
  color: grey;
  background-color: transparent;
  outline: none;
  font-size: 1rem;
}

.flat:hover,
.flat:active {
  color: rgb(0, 91, 70);
}
</style>
