<script setup>
import Navbar from './components/Navbar.vue'
import Hero from './components/Hero.vue'
import Project from './components/Projects.vue'
import About from './components/About.vue'
import Contact from './components/Contact.vue'

</script>

<template>
  <Navbar />
  <main class="space-y-32">
    <Hero />
    <About />
    <Project />
    <Contact />
  </main>
</template>

<style scoped>

</style>