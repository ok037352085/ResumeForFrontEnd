<script setup>
import { ref } from 'vue'
import emailjs from '@emailjs/browser'

const currentYear = ref(new Date().getFullYear())

const name = ref('')
const email = ref('')
const message = ref('')
const loading = ref(false)


const sendMessage = async () => {
    if(!name.value || !email.value || !message.value){
        alert('請完整填寫所有欄位!')
        return
    }

    loading.value = true

    try{
        await emailjs.send(
            import.meta.env.VITE_EMAILJS_SERVICE_ID,
            import.meta.env.VITE_EMAILJS_TEMPLATE_ID,
            {
                name: name.value,
                email: email.value,
                message: message.value
            },
            import.meta.env.VITE_EMAILJS_PUBLIC_KEY
        )

        alert('信件已成功寄出，我會盡快回復!')
        name.value = ''
        email.value = ''
        message.value = ''
    }catch(err){
        console.error(err)
        alert('寄送失敗，請稍後再試試!')
    }finally{
        loading.value = false
    }
}
</script>

<template>
    <section class="contact-footer">
        <div class="contact-section">
            <h2>Contact Me</h2>
            <p>有合作或面試邀約歡迎聯絡我!</p>

            <form class="contact-form" @submit.prevent="sendMessage">
                <input v-model="name" type="text" placeholder="姓名" />
                <input v-model="email" type="email" placeholder="Email" />
                <textarea v-model="message" rows="4" placeholder="留言"></textarea>
                <button type="submit" :disabled="loading">{{ loading ? '寄送中...' : '送出' }}</button>
            </form>
        </div>
        
        <footer class="footer">
            <p>© {{ currentYear }} Jim Yeh. All rights reserved.</p>
            <div class="social-links">
                <a href="https://github.com/ok037352085" target="_blank" aria-label="GitHub">
                    <i class="fab fa-github"></i>
                </a>
                <a href="https://www.linkedin.com/in/勁桐-葉-4847ba385/" target="_blank" aria-label="LinkedIn">
                    <i class="fab fa-linkedin"></i>
                </a>
                <a href="mailto:ok037352085@gmail.com" target="_blank" aria-label="Email">
                    <i class="fas fa-envelope"></i>
                </a>
            </div>
        </footer>
    </section>
</template>

<style scoped>
    .contact-footer {
        background: #f7e2b7;
        color: #331900;
        padding: 50px 20px 20px;
        display: flex;
        flex-direction: column;
        align-items: center;
        gap: 40px;
    }

    .contact-section {
        max-width: 600px;
        width: 100%;
        text-align: center;
    }

    .contact-section h2 {
        font-size: 2rem;
        margin-bottom: 10px;
    }

    .contact-section p {
        margin-bottom: 20px;    
    }

    .contact-form {
        display: flex;
        flex-direction: column;
        gap: 12px;
    }

    .contact-form input,
    .contact-form textarea {
        padding: 10px;
        border-radius: 10px;
        border: none;
        outline: none;
    }

    .contact-form button {
        background-color: #2a1e17;
        color: white;
        font-weight: 600;
        padding: 10px;
        border-radius: 10px;
        border: none;
        cursor: pointer;
        transition: 0.2s ease;
    }

    .contact-form button:hover {
        background-color: #be4600;
    }

    .footer {
        display: flex;
        flex-direction: column;
        align-items: center;
        gap: 12px;
        font-size: 14px;
    }

    .social-links {
        display: flex;
        gap: 15px;
    }

    .social-links a {
        color: #2a1e17;
        font-size: 1.5rem;
        transition: color 0.2s ease;
    }

    .social-links a:hover {
        color: #be4600;
    }
</style>