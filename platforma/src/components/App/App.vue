<template>
  <div class="app font-monospace">
    <div class="content">
      <Appinfo
        :allMoviesCount="movies.length"
        :favouriteMoviesCount="movies.filter((c) => c.favourite).length"
      />
      <div class="search-panel">
        <Searchpanel />
        <Appfilter />
      </div>
      <Movielist :movies="movies" />
      <Movieaddform @createMovie="createMovie" />
    </div>
  </div>
</template>
<script>
import Appinfo from "../app-info/Appinfo.vue";
import Searchpanel from "../search-panel/Searchpanel.vue";
import Appfilter from "../app-filter/Appfilter.vue";
import Movielist from "../movie-list/Movielist.vue";
import Movieaddform from "../movie-add-form/Movieaddform.vue";
export default {
  components: {
    Appinfo,
    Searchpanel,
    Appfilter,
    Movielist,
    Movieaddform,
  },
  data() {
    // Movielistitem uchun massiv
    return {
      movies: [
        { name: "Amar", viewers: "811", favourite: true, like: false, id: 1, },
        { name: "Akbar", viewers: "711", favourite: false, like: true, id: 1, },
        { name: "Antoni", viewers: "611", favourite: true, like: false, id: 1, },
      ],
    };
  },
  methods: {
    createMovie(item) {
        this.movies.push(item);
    },
  },
};
</script>
<style scoped>
.app {
  width: 100vw;
  color: black;
}
.content {
  width: 1000px;
  min-height: 700px;
  background: #fff;
  margin: 0 auto;
  padding: 5rem 0;
}
.search-panel {
  margin-top: 2rem;
  padding: 1.5rem;
  background-color: #fcfaf5;
  border-radius: 4px;
  box-shadow: 15px 15px 15px rgba(0, 0, 0, 0.15);
  border: 0.1px solid rgba(0, 0, 0, 0.15);
}
</style>
