<script setup>
  import { ref, onMounted, onBeforeUnmount } from 'vue'

  const showHeader = ref(true)
  const hamburger = ref(false)

  let lastScrollY = 10
  
  const toggleMenu = () => {
    hamburger.value = !hamburger.value
  }

  const closeMenu = () => {
    hamburger.value = false
  }

  const handleScroll = () => {
    const currentScrollY = window.scrollY

    if(currentScrollY > lastScrollY && currentScrollY > 50){
      showHeader.value = false
    }else {
      showHeader.value = true
    }

    lastScrollY = currentScrollY
    //如果漢堡選單開著，向下滾動也把它收起
    if(!showHeader.value) hamburger.value = false
  }

  const handleResize = () => {
    if(window.innerWidth > 960){
        hamburger.value = false
    }
  }

  onMounted(() => {
    window.addEventListener('scroll', handleScroll)
    window.addEventListener('resize', handleResize)
  })

  onBeforeUnmount(()=> {
    window.removeEventListener('scroll', handleScroll)
    window.removeEventListener('resize', handleResize)
  })
</script>

<template>
  <transition name="header-slide">
    <header v-if="showHeader">
      <div class="title">
        <h1>My Resume</h1>
      </div>
  
      <div class="protal">
        <ul>
          <li><a href="#hero">Home</a></li>
          <li><a href="#about">About Me</a></li>
          <li><a href="#projects">Projects</a></li>
          <li><a href="#contact">Contact</a></li>
        </ul>
      </div>
  
      <div class="hamburger" @click="toggleMenu">
        <span></span>
        <span></span>
        <span></span>
      </div>
  
      <div class="hamburger-protal" v-if="hamburger">
          <ul @click="closeMenu">
          <li><a href="#hero">Home</a></li>
          <li><a href="#about">About Me</a></li>
          <li><a href="#projects">Projects</a></li>
          <li><a href="#contact">Contact</a></li>
          </ul>
      </div>
    </header>
  </transition>
</template>

<style scoped>
  header {
    background-color: #2a1e17;
    width: 100%;
    display: flex;
    justify-content: space-around;
    align-items: center;
    padding: 10px 20px;
    position: fixed;
    top: 0;
    left: 0;
    z-index: 50;
    transition: transform 0.3s ease;
  }

  .header-slide-enter-active,
  .header-slide-leave-active {
    transition: transform 0.3s ease, opacity 0.3s ease;
  }

  .header-slide-enter-from,
  .header-slide-leave-to {
    transform: translateY(-100%);
    opacity: 0;
  }

  .title {
    width: 100%;
    color: bisque;
  }

  .protal {
    width: 100%;
  }

  .protal ul {
    list-style: none;
    display: flex;
    justify-content: space-evenly;
    font-size: 20px;
    font-weight: 600;
  }

  .protal ul li a {
    color: bisque;
    text-decoration: none;
    transition: 0.2s ease-in-out;
  }

  .protal ul li a:hover {
    color: #be4600;
  }

  .hamburger {
    display: none;
    flex-direction: column;
    gap: 7px;
    cursor: pointer;
  }

  .hamburger span {
    border: 2px solid bisque;
    width: 40px;
    margin-right: 40px;
  }

  .hamburger-protal {
    position: fixed;
    right: 0;
    top: 60px;
    background-color: #2a1e17;
    color: bisque;
    padding: 20px;
    box-shadow: 0 4px 8px rgba(0,0,0,0.3);
  }

  .hamburger-protal ul {
    list-style: none;
    display: flex;
    flex-direction: column;
    gap: 20px;
  }

  .hamburger-protal ul li a{
    color: bisque;
    font-size: 20px;
    font-weight: 600;
    text-decoration: none;
  }

  @media screen and (max-width: 960px){
    .protal {
        display: none;
    }

    .hamburger {
        display: flex;
    }
  }
</style>
