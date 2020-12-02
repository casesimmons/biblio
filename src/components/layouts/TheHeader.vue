<template>
  <header>
    <div>{{ title }}</div>
  </header>
</template>

<script>
export default {
  props: ['title']
};
</script>

<style scoped>
header {
  width: 100%;
  height: 6rem;
  display: flex;
  justify-content: center;
  align-items: center;
}

header div {
  font-size: 2rem;
  color: white;
  text-shadow: 0 1px 8px pink;
  /* margin: 0; */
}
</style>
