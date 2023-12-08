<template>
  <div class="movie-list list-group">
    <Movielistitem v-for="movie in movies" v-bind:movie="movie" :key="movie.id"/>
  </div>
</template>
<script>
import Movielistitem from "../movie-list-item/Movielistitem.vue";
export default {
  components: {
    Movielistitem,
  },
  // Appdan kelayotgan massiv uchun props
  props:{
    movies: {
      type: Array,
      required: true,
    }
  }
};
</script>
<style scoped>
.movie-list {
  margin-top: 2rem;
  padding: 1.5rem;
  background-color: #fcfaf5;
  border-radius: 4px;
  box-shadow: 15px 15px 15px rgba(0, 0, 0, 0.15);
  border: 0.1px solid rgba(0, 0, 0, 0.15);
}
</style>
