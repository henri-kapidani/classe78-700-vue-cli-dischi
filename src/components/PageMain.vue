<template>
  <div>
    <CardMovie
      v-for="objMovie in arrDiscsFiltered"
      :key="objMovie.title"
      :movie-info="objMovie"
    />
  </div>
</template>

<script>
import axios from 'axios';
import CardMovie from '@/components/CardMovie.vue';

export default {
  name: 'PageMain',
  components: {
    CardMovie,
  },
  props: {
    genreFilter: String,
  },
  data() {
    return {
      urlApi: 'https://flynn.boolean.careers/exercises/api/array/music',
      arrDiscs: null,
    };
  },
  computed: {
    arrGenres() {
      const arrGenres = [];
      if (this.arrDiscs) {
        this.arrDiscs.forEach((objDisc) => {
          if (!arrGenres.includes(objDisc.genre)) {
            arrGenres.push(objDisc.genre);
          }
        });
      }
      // console.log(arrGenres);
      return arrGenres;
    },
    arrDiscsFiltered() {
      if (this.genreFilter === 'all') {
        return this.arrDiscs;
      }
      return this.arrDiscs.filter((objDisc) => objDisc.genre === this.genreFilter);
    },
  },
  watch: {
    arrGenres(newValue) {
      this.$emit('genresReady', newValue);
    },
  },
  created() {
    axios.get(this.urlApi)
      .then((axiosResponse) => {
        console.log(axiosResponse);
        this.arrDiscs = axiosResponse.data.response;
      });
  },
};
</script>

<style lang="scss" scoped>

</style>
