<template>
  <ul>
    <li>{{ movieInfo.poster }}</li>
    <li>{{ movieInfo.title }}</li>
    <li>{{ movieInfo.author }}</li>
    <li>{{ movieInfo.genre }}</li>
    <li>{{ movieInfo.year }}</li>
  </ul>
</template>

<script>
export default {
  name: 'CardMovie',
  props: {
    movieInfo: Object,
  },
};
</script>

<style lang="scss" scoped>

</style>
