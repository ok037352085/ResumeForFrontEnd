<script setup>
import { ref } from 'vue'
const currentYear =  ref(new Date().getFullYear())
</script>

<template>
  <footer class="footer">
    <div class="footer-content">
      <p>© {{ currentYear }} Jim Yeh. All rights reserved.</p>

      <div class="social-links">
        <a href="https://github.com/ok037352085" target="_blank" aria-label="GitHub">
          <i class="fab fa-github"></i>
        </a>
        <a href="https://www.linkedin.com/in/勁桐-葉-4847ba385/" target="_blank" aria-label="LinkedIn">
          <i class="fab fa-linkedin"></i>
        </a>
        <a href="mailto: ok037352085@gmail.com" aria-label="Email">
          <i class="fas fa-envelope"></i>
        </a>
      </div>
    </div>
  </footer>
</template>

<style scoped>
.footer {
  background-color: #331900;
  color: bisque;
  text-align: center;
  padding: 20px;
  margin-top: 40px;
  font-size: 14px;
}

.footer-content {
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 12px;
}

.social-links {
  display: flex;
  gap: 15px;
}

.social-links a {
  color: bisque;
  font-size: 1.5rem;
  transition: color 0.2s ease;
}

.social-links a:hover {
  color: #be4600;
}
</style>
