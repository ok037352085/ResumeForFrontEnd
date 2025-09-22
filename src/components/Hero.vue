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
        <h2>我是葉勁桐</h2>
        <p>熱愛探索新事物並持續學習新技術，善於思考與解決問題，同時重視開發效率。<br/>喜歡團隊合作的氛圍，樂於分享與討論程式設計及相關知識，並具備後端資料庫的基礎知識，有助於與後端團隊順暢溝通，提升專案整體協作效率。</p>
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
