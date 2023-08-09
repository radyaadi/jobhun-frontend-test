<script>
import axios from 'axios';
export default {
  data() {
    return { movies: [] };
  },
  mounted() {
    axios.get('https://api.tvmaze.com/search/shows?q=girls').then((res) => {
      this.movies = res.data;
    });
  },
};
</script>

<template>
  <div class="movies">
    <div class="movie__item" v-for="movie in movies" :key="movie.show.id">
      <div class="movie-item__header">
        <img
          class="movie-item__header-poster"
          :alt="movie.show.name"
          :src="movie.show.image.medium"
        />
        <div class="movie-item__header-rating">
          <p>
            ⭐️<span class="movie-item__header-rating-score">
              {{
                movie.show.rating.average
                  ? movie.show.rating.average
                  : 'Unrated'
              }}
            </span>
          </p>
        </div>
      </div>
      <div class="movie-item__content">
        <h3>
          {{ movie.show.name }}
        </h3>
        <p v-html="movie.show.summary"></p>
      </div>
    </div>
  </div>
</template>
