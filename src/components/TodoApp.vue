<template>
  <div class="demo">
    <button @click="toggleTheme" :class="themeClasses">切換主題</button>

    <div :class="cardClasses" class="card">
      <h3>{{ title }}</h3>
      <p>當前主題：{{ isDark ? '深色' : '淺色' }}</p>
      <p>狀態：{{ status }}</p>
    </div>

    <button @click="toggleStatus" :class="statusButtonClasses">
      {{ statusButtonText }}
    </button>
  </div>
</template>

<script setup>
import { ref, computed } from 'vue'

// 響應式數據
const isDark = ref(false)
const isActive = ref(false)
const title = ref('Vue 響應式示例')

// 計算屬性
const status = computed(() => (isActive.value ? '激活' : '未激活'))

const themeClasses = computed(() => ({
  'btn-dark': isDark.value,
  'btn-light': !isDark.value,
  'theme-btn': true,
}))

const cardClasses = computed(() => [
  'demo-card',
  {
    'dark-theme': isDark.value,
    'light-theme': !isDark.value,
    'active-card': isActive.value,
  },
])

const statusButtonClasses = computed(() => ({
  btn: true,
  'btn-success': isActive.value,
  'btn-secondary': !isActive.value,
}))

const statusButtonText = computed(() => (isActive.value ? '停用' : '啟用'))

// 方法
const toggleTheme = () => {
  isDark.value = !isDark.value
}

const toggleStatus = () => {
  isActive.value = !isActive.value
}
</script>

<style scoped>
.demo {
  padding: 20px;
}

.card {
  margin: 20px 0;
  padding: 20px;
  border-radius: 8px;
  transition: all 0.3s ease;
}

.light-theme {
  background-color: #ffffff;
  color: #333333;
  border: 1px solid #e0e0e0;
}

.dark-theme {
  background-color: #2d3748;
  color: #ffffff;
  border: 1px solid #4a5568;
}

.active-card {
  box-shadow: 0 4px 12px rgba(0, 123, 255, 0.3);
  border-color: #007bff;
}

.btn {
  padding: 10px 20px;
  border: none;
  border-radius: 4px;
  cursor: pointer;
  margin: 0 10px;
  transition: all 0.2s ease;
}

.btn-dark {
  background-color: #343a40;
  color: white;
}

.btn-light {
  background-color: #f8f9fa;
  color: #343a40;
}

.btn-success {
  background-color: #28a745;
  color: white;
}

.btn-secondary {
  background-color: #6c757d;
  color: white;
}

.btn:hover {
  opacity: 0.8;
}
</style>
