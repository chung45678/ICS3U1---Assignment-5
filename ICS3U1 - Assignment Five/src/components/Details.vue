<script setup>
import axios from "axios";
import { ref, onMounted } from "vue";

const props = defineProps({ movieId: { type: Number, required: true } });
const response = ref(null)

onMounted(async () => {
  response.value = await axios.get(`https://api.themoviedb.org/3/movie/${props.movieId}?api_key=${import.meta.env.VITE_API_KEY}&append_to_response=videos`);
})
</script>

<template>
  <div v-if="response" class="movie-detail">
    <div class="movie-poster-container">
      <img :src="`https://image.tmdb.org/t/p/w500${response.data.poster_path}`" alt="Movie Poster"
        class="movie-poster" />
      <p class="tag-line">{{ response.data.tagline }}</p>
    </div>

    <div class="movie-details">
      <h1 class="movie-title">{{ response.data.original_title }}</h1>
      <p class="movie-overview">{{ response.data.overview }}</p>
      <p class="release-date">Release Date:  {{ response.data.release_date }}</p>
      <p class="origin-country">Origin Country:  {{ response.data.origin_country[0] }}</p>
      <p class="vote-average">Vote Average:  {{ response.data.vote_average }}</p>
      <a class="movie-site" :href="response.data.homepage" target="_blank">Official Movie Site</a>
    </div>
  </div>

  <div v-if="response" class="trailers">
    <h2 class="trailers-title">Trailers</h2>
    <div class="trailers-container">
      <div v-for="trailer in response.data.videos.results" :key="trailer.id" class="trailer-tile">
        <a :href="`https://www.youtube.com/watch?v=${trailer.key}`" target="_blank">
          <img :src="`https://img.youtube.com/vi/${trailer.key}/hqdefault.jpg`" alt="Trailer"
            class="trailer-thumbnail" /></a>
      </div>
    </div>
  </div>
</template>

<style scoped>
</style>