<script setup>
import { RouterLink, useRouter } from 'vue-router';
import { ref } from 'vue';
import Header from '../components/Header.vue';
import Footer from '../components/Footer.vue';

const router = useRouter();
const password = ref('');

const handleLogin = () => {
  if (password.value === "chung") {
    router.push("/movies");
  } else {
    alert("Invalid Password");
  }
};
</script>

<template>
  <Header />
  <div class="overlay">
    <div class="form-container">
      <h2>Login to Your Account</h2>
      <form @submit.prevent="handleLogin">
        <input type="email" placeholder="Email" class="input-field" required />
        <input v-model:="password" type="password" placeholder="Password" class="input-field" required />
        <button type="submit" class="button login">Login</button>
      </form>
    </div>
  </div>
  <Footer />
</template>

<style scoped>

.navbar {
  width: 100%;
  padding: 20px;
  display: flex;
  justify-content: space-between;
  align-items: center;
  background-color: rgba(255, 255, 255, 0.1);
  box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
}

.navbar h1 {
  font-size: 2rem;
  color: white;
  margin: 0;
}

.navbar .button.register {
  padding: 10px 20px;
  border: 2px solid white;
  background-color: transparent;
  color: white;
  text-transform: uppercase;
  font-weight: bold;
  text-decoration: none;
  border-radius: 4px;
  transition: background-color 0.3s ease, color 0.3s ease;
}

.navbar .button.register:hover {
  background-color: white;
  color: red;
}

body {
  margin: 0;
  font-family: Arial, sans-serif;
  background-color: #fff;
  color: #333;
}

.hero {
  height: 100vh;
  display: flex;
  align-items: center;
  justify-content: center;
  background: black;
}

.overlay {
  width: 100%;
  height: 100%;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  color: white;
}


.form-container {
  background-color: white;
  padding: 30px 20px;
  border-radius: 8px;
  box-shadow: 0 8px 16px rgba(0, 0, 0, 0.2);
  text-align: center;
  width: 90%;
  max-width: 400px;
}

.form-container h2 {
  margin-bottom: 20px;
  color: red;
}

.input-field {
  width: 100%;
  padding: 10px;
  margin: 10px 0;
  border: 2px solid red;
  border-radius: 4px;
  outline: none;
}

.input-field:focus {
  border-color: darkred;
  box-shadow: 0 0 5px rgba(255, 0, 0, 0.5);
}

.button.login {
  width: 100%;
  padding: 10px;
  background-color: red;
  color: white;
  text-transform: uppercase;
  font-weight: bold;
  border: none;
  border-radius: 4px;
  cursor: pointer;
  transition: background-color 0.3s ease;
}

.button.login:hover {
  background-color: darkred;
}
</style>