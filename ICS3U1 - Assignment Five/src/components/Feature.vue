// components/Feature.vue
<template>
  <section>
    <h3>Now Playing</h3>
    <div v-for="movie in movies" :key="movie.id">
      <h4>{{ movie.title }}</h4>
      <img :src="`https://image.tmdb.org/t/p/w500/${movie.poster_path}`" alt="Movie poster">
    </div>
  </section>
</template>

<script setup>
import { ref, onMounted } from 'vue';
import axios from 'axios';

const { data: nowPlaying } = await axios.get(`https://api.themoviedb.org/3/movie/now_playing?api_key=${import.meta.env.VITE_TMDB_KEY}`);
</script>

