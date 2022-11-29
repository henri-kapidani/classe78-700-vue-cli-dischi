<template>
  <div>
    <CardMovie
      v-for="objMovie in arrMovies"
      :key="objMovie.title"
      :movie-info="objMovie"
    />
  </div>
</template>

<script>
import CardMovie from '@/components/CardMovie.vue';

export default {
  name: 'PageMain',
  components: {
    CardMovie,
  },
  props: {
    arrMovies: Array,
  },
};
</script>

<style lang="scss" scoped>

</style>
