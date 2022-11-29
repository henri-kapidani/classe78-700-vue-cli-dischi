<template>
  <div>
    <PageMain :arr-movies="movies" />
  </div>
</template>

<script>
import axios from 'axios';
import PageMain from '@/components/PageMain.vue';

export default {
  name: 'App',
  components: {
    PageMain,
  },
  data() {
    return {
      urlApi: 'https://flynn.boolean.careers/exercises/api/array/music',
      movies: null,
    };
  },
  created() {
    axios.get(this.urlApi)
      .then((axiosResponse) => {
        console.log(axiosResponse);
        this.movies = axiosResponse.data.response;
      });
  },
};
</script>

<style lang="scss">
@import "~bootstrap/scss/bootstrap";

body {
  background-color: salmon;
}
</style>
