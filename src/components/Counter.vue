<script setup>
import { ref, computed } from 'vue'

const count = ref(0)

const status = computed(() => {
  if (count.value === 0) return '🚀 開始計數吧！'
  if (count.value < 5) return '📈 還很少'
  if (count.value < 10) return '🔥 越來越多了'
  if (count.value < 20) return '💪 數量很高了！'
  return '🎉 哇！超過 20 了！'
})

const increment = () => count.value++
const decrement = () => { if (count.value > 0) count.value-- }
const reset = () => count.value = 0
</script>

<template>
  <div class="bg-gradient-to-br from-blue-500 to-purple-600 text-white p-8 rounded-2xl shadow-xl">
    <h2 class="text-2xl font-bold text-center mb-6">計數器範例</h2>
    
    <div class="text-center mb-8">
      <span class="text-6xl font-bold block mb-2 transition-all duration-300" 
            :class="{ 'text-red-300 scale-110': count > 10 }">
        {{ count }}
      </span>
      <p class="text-lg opacity-90">{{ status }}</p>
    </div>
    
    <div class="flex flex-wrap gap-3 justify-center">
      <button @click="decrement" 
              :disabled="count <= 0"
              class="bg-red-500 hover:bg-red-600 disabled:opacity-50 disabled:cursor-not-allowed 
                     px-6 py-3 rounded-lg font-semibold transition-all duration-200 
                     hover:scale-105 hover:shadow-lg min-w-[120px]">
        減少 (-)
      </button>
      <button @click="increment"
              class="bg-green-500 hover:bg-green-600 px-6 py-3 rounded-lg font-semibold 
                     transition-all duration-200 hover:scale-105 hover:shadow-lg min-w-[120px]">
        增加 (+)
      </button>
      <button @click="reset"
              class="bg-gray-500 hover:bg-gray-600 px-6 py-3 rounded-lg font-semibold 
                     transition-all duration-200 hover:scale-105 hover:shadow-lg min-w-[120px]">
        重置
      </button>
    </div>
    
    <div v-if="count > 10" 
         class="mt-6 p-4 bg-red-500/20 border-2 border-red-400 rounded-lg text-center 
                font-bold animate-pulse">
      ⚠️ 數值已超過 10！
    </div>
  </div>
</template>
