<template>
    <section>
      <label for="genres">Select a Genre:</label>
      <select id="genres" @change="fetchMovies">
        <option v-for="genre in genres" :key="genre.id" :value="genre.id">{{ genre.name }}</option>
      </select>
      <div v-for="movie in movies" :key="movie.id">
        <h4>{{ movie.title }}</h4>
        <img :src="`https://image.tmdb.org/t/p/w500/${movie.poster_path}`" alt="Movie poster">
      </div>
    </section>
  </template>
  <script>
  import { ref } from 'vue';
  import axios from 'axios';
  
  export default {
    props: ['genres'],
    setup(props) {
      const movies = ref([]);
  
      const fetchMovies = async (event) => {
        const genreId = event.target.value;
        const response = await axios.get(
          `https://api.themoviedb.org/3/discover/movie?api_key=YOUR_API_KEY&with_genres=${genreId}`
        );
        movies.value = response.data.results;
      };
  
      return { genres: props.genres, movies, fetchMovies };
    },
  };
  </script>