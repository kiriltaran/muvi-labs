<template>
  <div class="movie-related">
    <div 
      v-if="isVisibleTitle" 
      class="title">Related movies</div>
    <el-row :gutter="20">
      <el-col 
        v-for="movie in movies" 
        :key="movie.id"
        :span="6"
      >
        <movie-card :movie="movie" />
      </el-col>
    </el-row>
  </div>
</template>

<script>
import MovieCard from '@/components/MovieCard.vue';

export default {
  name: 'MovieRelated',
  components: {
    MovieCard,
  },
  props: {
    movies: {
      type: Array,
      default() {
        return [];
      },
    },
  },
  computed: {
    isVisibleTitle() {
      return this.movies.length > 0;
    },
  },
};
</script>

<style lang="scss" scoped>
.title {
  font-size: 24px;
  margin-bottom: 20px;
}
</style>


