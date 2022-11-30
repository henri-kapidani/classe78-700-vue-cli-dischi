<template>
  <div>
    <PageHeader
      :genres-list="genresList"
      @changedGenre="genreChange"
    />
    <PageMain
      :genre-filter="genreFilter"
      @genresReady="getGenresList"
    />
  </div>
</template>

<script>
import PageHeader from '@/components/PageHeader.vue';
import PageMain from '@/components/PageMain.vue';

export default {
  name: 'App',
  components: {
    PageHeader,
    PageMain,
  },
  data() {
    return {
      genresList: [],
      genreFilter: 'all',
    };
  },
  methods: {
    getGenresList(genresList) {
      this.genresList = genresList;
    },
    genreChange(genreFilter) {
      this.genreFilter = genreFilter;
    },
  },
};
</script>

<style lang="scss">
@import "~bootstrap/scss/bootstrap";

body {
  background-color: salmon;
}
</style>
