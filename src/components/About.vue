<script setup>

</script>

<template>
    <section id="about" class="about-section">
        <div class="about-decoration"></div>

        <div class="about-content">
            <h5 class="about-title">關於我：我是個怎麼樣的人</h5>
            <h4 class="about-text">
                我是一名前端工程師，熱愛學習新技術並持續探索最新的開發工具，擅長使用 Vue 3 及 React 進行專案開發，並熟悉 API 串接與 Git 版本控制。
                在專案開發過程中，我能獨立完成前端功能，並重視程式碼的可讀性與維護性。我喜歡思考與解決問題，並持續優化開發流程，喜歡運用 Prompt Engineering 搭配 AI 工具輔助開發，提升工作效率。
                我很喜歡團隊合作的氛圍，樂於分享與討論程式設計與相關知識，並具備後端資料庫的基礎知識，有助於與後端工程師溝通順暢，促進專案進度。
                目前正積極尋找前端工程師的職位，期望能加入重視學習與創新的團隊，發揮專業能力並持續成長。
            </h4>
        </div>
    </section>
</template>

<style scoped>
.about-section {
    position: relative;
    min-height: 100vh;
    background-color: #f7e2b7;
    display: flex;
    align-items: flex-end;
    padding: 80px 60px 40px;
    overflow: hidden;
    }

.about-content {
    position: relative;
    z-index: 2;
    max-width: 1200px;
}

.about-title {
    font-size: 30px;
    font-weight: 500;
    margin-bottom: 20px;
}

.about-text {
    font-size: 32px;
    line-height: 1.4;
}

.about-decoration {
    position: absolute;
    top: 10%;
    right: 0;
    bottom: 0;
    left: 0;
    background: url('../assets/bgline02.png');
}
@media screen and (max-width: 960px) {
    .about-section {
        grid-template-columns: 1fr;
        padding: 60px 20px;
    }
    .about-content {
        align-self: start;
    }
    .about-text {
        font-size: 20px;
    }
}
</style>