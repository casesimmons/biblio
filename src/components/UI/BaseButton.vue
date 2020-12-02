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
  font-size: 1rem;
}

button:hover,
button:active {
  color: red;
  border-style: none;
  font-size: 1rem;
  cursor: not-allowed;
}

.flat {
  background-color: transparent;
  color: #3a0061;
  border: none;
}

.flat:hover,
.flat:active {
  background-color: #edd2ff;
}
</style>
