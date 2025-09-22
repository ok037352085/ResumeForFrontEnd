<script setup>
    import { ref } from 'vue'
    import TodoList from '/projectImg/TodoList.png'
    import WeatherAPI from '/projectImg/WeatherAPI.png'
    import SpotifyAPI from '/projectImg/SpotifyAPI.png'
    import TravelWebSite from '/projectImg/TravelWebSite.png'


    const projects = ref([
        {
            id: 1,
            title: '2025行事曆 & TodoList',
            description: '以Vue3 + Vite 製作，可點選日期管理每日代辦事項，支援新增、刪除，介面簡潔直覺。',
            image: TodoList,
            link: 'https://ok037352085.github.io/TodoList/'
        },
        {
            id: 2,
            title: '氣象查詢網站',
            description: '使用 Vue3 串接 OpenWeather API，支援城市搜尋、錯誤提示、Loading動畫，並針對手機進行 RWD',
            image: WeatherAPI,
            link: 'https://ok037352085.github.io/WeatherAPI/'
        },
        {
            id: 3,
            title: '音樂查找撥放網站',
            description: '使用Vue3 串接 Spotify API，提供spotify帳號的登入，音樂查找及撥放(網頁播放需要spotify premium會員)',
            image: SpotifyAPI,
            link: 'https://ok037352085.github.io/SpotifyAPI/'
        },
        {
            id: 4,
            title: '苗栗地方旅遊網站',
            description: '使用Vue3 + Firebase 打造會員註冊與登入功能，將網站demo的景點收藏排列組合成一個完整的行程並保存在會員帳號中，留言區及時同步更新，並支援跑馬燈顯示使用者留言。',
            image: TravelWebSite,
            link: 'https://ok037352085.github.io/TravelWebSite'
        }
    ])


</script>

<template>
    <section id="projects" class="projects">
        <h1 class="section-title">我的作品</h1>
        <div class="grid">
            <div class="card" v-for="project in projects">
                <img class="card-image" :src="project.image" :alt="project.title" />
                <div class="card-body">
                    <h3 class="card-title">{{ project.title }}</h3>
                    <p class="card-description">{{ project.description }}</p>
                    <a class="card-btn" :href="project.link" target="_blank" >查看作品</a>
                </div>
            </div>
        </div>
    </section>
</template>

<style scoped>
    .projects {
        padding: 60px 20px;
        background: #2a1e17;
    }

    .section-title {
        text-align: center;
        font-weight: bold;
        margin-bottom: 120px;
        color: bisque;
    }

    .grid {
        display: grid;
        grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
        gap: 20px;
    }

    .card {
        background: bisque;
        border-radius: 10px;
        box-shadow: 0 4px 8px rgba(0,0,0,0.2);
        overflow: hidden;
        display: flex;
        flex-direction: column;
        transition: transform 0.2s ease-in-out;
    }

    .card:hover {
        transform: translateY(-5px);
    }

    .card-image {
        width: 100%;
        height: 180px;
        object-fit: cover;
    }

    .card-body {
        padding: 20px;
    }

    .card-title {
        font-size: 20px;
        font-weight: 600;
        margin-bottom: 10px;
    }

    .card-description {
        font-size: 18px;
        color: #333;
        margin-bottom: 10px;
    }

    .card-btn {
        display: inline-block;
        padding: 8px 16px;
        background: #2a1e17;
        color: bisque;
        border-radius: 10px;
        text-decoration: none;
        font-weight: bold;
        transition: background 0.2s;
        cursor: pointer;
    }
    .card-btn:hover {
        background: #be4600;
    }
</style>