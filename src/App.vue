<script setup>
import Navbar from './components/Navbar.vue'
import Heroes from './components/Heroes.vue'
import About from './components/About.vue'
import Footer from './components/Footer.vue'

import { onMounted } from 'vue'

onMounted(() => {
  document.title = "Absurd Comment API";
})
</script>

<template>
  <div class="flex flex-col min-h-screen w-full">
    <Navbar />
    <Heroes />
    <About />
    <Footer />
  </div>
</template>

<style scoped>
/* header {
  line-height: 1.5;
}

.logo {
  display: block;
  margin: 0 auto 2rem;
}

@media (min-width: 1024px) {
  header {
    display: flex;
    place-items: center;
    padding-right: calc(var(--section-gap) / 2);
  }

  .logo {
    margin: 0 2rem 0 0;
  }

  header .wrapper {
    display: flex;
    place-items: flex-start;
    flex-wrap: wrap;
  }
} */
</style>
