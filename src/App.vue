<script setup>
// import { RouterLink, RouterView } from 'vue-router';
</script>

<template>
  <header>
    <div class="header__brand container">
      <h1>Tv Maze</h1>
    </div>
  </header>
  <main class="container">
    <RouterView />
  </main>
  <footer>
    <p>
      Created by
      <a
        href="https://radya-profile-web.netlify.app/"
        target="_blank"
        rel="noreferrer"
        >Radya Adi</a
      >
    </p>
  </footer>
</template>
