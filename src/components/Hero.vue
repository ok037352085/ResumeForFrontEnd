<script setup>
  // 這裡不需要寫什麼，只有靜態內容
</script>

<template>
  <section id="hero" class="hero">
    <div class="hero-content">
      <div class="hero-image">
        <img src="../assets/myPicsmaller.jpg" alt="My portrait" />
      </div>

      <div class="hero-text">
        <h1>Hi, I’m Jim.</h1>
        <h2>Front-End Developer</h2>
        <h3>專長：Vue 3 • React • API Integration • RWD • Git</h3>
        <p>
          大學主修遊戲程式設計，畢業後自學前端技術，擅長使用Vue3及React框架協助開發網站，具備 API 串接經驗並使用 Git 進行版本控管。
          喜歡學習新技術並應用於專案，透過實作不斷精進。曾完成互動式技能圖表、天氣查詢網站、全年行事曆、旅遊網站和網路商店，皆已公開部署至Github Pages。
        </p>
        <div class="hero-btn">
          <button><a href="#projects">查看作品</a></button>
          <button><a href="#contact">聯絡我</a></button>
      </div>
      </div>
    </div>
  </section>
</template>

<style scoped>
.hero {
  background-color: #2a1e17;
  color: #f5e1c8;
  display: flex;
  align-items: center;
  justify-content: space-evenly;
  padding: 80px;
}

.hero-content {
  display: flex;
  flex-direction: row;
  align-items: center;
  justify-content: center;
  width: 100%;
  gap: 60px;
}

.hero-image img {
  max-width: 650px;
  width: 100%;
  border-radius: 12px;
  object-fit: cover;
}

.hero-text h1 {
  font-size: 3rem;
  margin-bottom: 10px;
  font-weight: bold;
}

.hero-text h2 {
  font-size: 2.5rem;
  margin-bottom: 20px;
  font-weight: 500;
}

.hero-text p {
  font-size: 1.3rem;
  line-height: 1.6;
  max-width: 500px;
  padding-top: 10px;
}

button {
  display: inline-block;
  margin: 10px;
  padding: 8px 16px;
  background: bisque;
  color: #2a1e17;
  border-radius: 10px;
  transition: background 0.2s;
  cursor: pointer;
  border: none;
}

button:hover {
  background: #be4600;
}

button a {
  color: #2a1e17;
  text-decoration: none;
  font-weight: 900;
}

/* RWD：手機時改成上下排 */
@media screen and (max-width: 960px) {
  .hero-content {
    flex-direction: column;
    text-align: center;
  }

  .hero-text h1 {
    font-size: 2.2rem;
  }

  .hero-text h2 {
    font-size: 1.8rem;
  }
}
</style>
