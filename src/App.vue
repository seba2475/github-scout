<template>
  <div class="page">
    <div class="card">
      <h1>GitHub Scout</h1>
      <p class="subtitle">輸入 GitHub 帳號，查詢使用者公開資料</p>

      <div class="search-box">
        <input
          v-model="username"
          type="text"
          placeholder="請輸入 GitHub 帳號"
          @keyup.enter="fetchUser"
        />

        <button @click="fetchUser" :disabled="loading">
          {{ loading ? '查詢中...' : '查詢' }}
        </button>
      </div>

      <p v-if="message" class="message">{{ message }}</p>

      <div v-if="user" class="user-card">
        <img :src="user.avatar_url" alt="GitHub avatar" class="avatar" />
        <h2>{{ user.name || user.login }}</h2>
        <p class="login">@{{ user.login }}</p>
        <p class="bio">{{ user.bio || '這位使用者沒有留下個人簡介。' }}</p>
        <a :href="user.html_url" target="_blank">前往 GitHub 個人頁面</a>
      </div>
    </div>
  </div>
</template>

<script setup>
import { ref } from 'vue'

const username = ref('')
const user = ref(null)
const message = ref('')
const loading = ref(false)

const fetchUser = async () => {
  user.value = null
  message.value = ''

  if (!username.value.trim()) {
    message.value = '請先輸入 GitHub 帳號'
    return
  }

  loading.value = true

  try {
    const res = await fetch(`https://api.github.com/users/${username.value}`)

    if (!res.ok) {
      throw new Error('Not Found')
    }

    const data = await res.json()
    user.value = data
  } catch (error) {
    message.value = '查無此人'
  } finally {
    loading.value = false
  }
}
</script>

<style scoped>
.page {
  min-height: 100vh;
  margin: 0;
  background: linear-gradient(135deg, #0f172a, #1e293b);
  display: flex;
  justify-content: center;
  align-items: center;
  padding: 24px;
  font-family: Arial, Helvetica, sans-serif;
}

.card {
  width: 100%;
  max-width: 520px;
  background: #ffffff;
  border-radius: 20px;
  padding: 32px;
  box-shadow: 0 20px 50px rgba(0, 0, 0, 0.25);
  text-align: center;
}

h1 {
  margin-bottom: 8px;
}

.subtitle {
  color: #555;
  margin-bottom: 20px;
}

.search-box {
  display: flex;
  gap: 10px;
  margin-bottom: 16px;
}

input {
  flex: 1;
  padding: 12px;
  border: 1px solid #ccc;
  border-radius: 10px;
  font-size: 16px;
}

button {
  padding: 12px 16px;
  border: none;
  background: #2563eb;
  color: white;
  border-radius: 10px;
  cursor: pointer;
  font-size: 16px;
}

button:disabled {
  background: #94a3b8;
  cursor: not-allowed;
}

.message {
  color: #dc2626;
  font-weight: bold;
  margin: 12px 0;
}

.user-card {
  margin-top: 24px;
  padding: 20px;
  border-radius: 16px;
  background: #f8fafc;
}

.avatar {
  width: 140px;
  height: 140px;
  border-radius: 50%;
  object-fit: cover;
  margin-bottom: 16px;
  border: 4px solid #cbd5e1;
}

.login {
  color: #475569;
  margin-bottom: 10px;
}

.bio {
  margin: 12px 0 16px;
  color: #334155;
}

a {
  color: #2563eb;
  text-decoration: none;
  font-weight: bold;
}
</style>