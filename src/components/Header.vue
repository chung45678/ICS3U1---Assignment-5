<script setup>
import { RouterLink } from 'vue-router';
</script>


<template>
  <div class="header">
    <RouterLink to="/" class="logo-link"><img src="/src/assets/logo.png" class="logo" alt="Logo" /></RouterLink>
    <ul>
      <li><a href="">Trending</a></li>
      <li><a href="">TV Shows</a></li>
      <li>
        <RouterLink to="/movies" class = "movies">Movies</RouterLink>
      </li>
      <li>
        <RouterLink to="/register" class="entry">Join Now</RouterLink>
      </li>
      <li>
        <RouterLink to="/login" class="entry">Log In</RouterLink>
      </li>
    </ul>
  </div>
</template>


<style scoped>
.header {
  background-color: #000000;
  padding: 10px 20px;
  display: flex;
  justify-content: space-between;
  align-items: center;
  
}

.header ul {
  list-style-type: none;
  display: flex;
  align-items: center;
  
}

.header li {
  margin: 0 10px;
  font-weight: bold;
  padding: 5px;

  color: rgb(0, 0, 0);
}

.header a {
  text-decoration: none;
  font-size: 16px;
  transition: 0.3s;
  color: rgb(255, 255, 255);
}

.logo {
  width: 150px;
  height: auto;
}

.entry {
  background-color: rgb(255, 0, 0);
  color: rgb(0, 0, 0);
  padding: 10px 20px;
  font-size: 16px;
  font-weight: bold;
  transition: 0.3s;
  border-radius: 30px;
  text-decoration: none;
  display: inline-block;
  text-align: center;
}

.entry:hover {
  background-color: rgb(81, 1, 1);
}
</style>