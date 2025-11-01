<template>
  <div class="min-h-screen bg-gradient-to-b from-amber-50 to-yellow-100 flex flex-col items-center justify-center text-center font-['Pretendard']">
    <!-- 상단 제목 -->
    <h1 class="text-5xl md:text-6xl font-bold text-amber-700 mb-6 animate-fade-in">
      🌕 한가위 잘 보내세요 🌾
    </h1>

    <!-- 달 이미지 -->
    <div class="relative">
      <div class="w-48 h-48 md:w-64 md:h-64 bg-yellow-300 rounded-full shadow-lg animate-pulse"></div>
      <div class="absolute inset-0 flex items-center justify-center">
        <span class="text-2xl md:text-3xl text-amber-900 font-semibold tracking-wide">
          보름달처럼 풍성한 하루 되세요!
        </span>
      </div>
    </div>

    <!-- 문구 -->
    <p class="mt-10 text-lg md:text-xl text-amber-800 leading-relaxed max-w-lg">
      가족과 함께 웃음 가득한 추석 보내시고, <br />
      마음의 보름달도 환하게 차오르길 바랍니다 🌝
    </p>

    <!-- 버튼 -->
    <button
        @click="showMessage = !showMessage"
        class="mt-10 px-6 py-3 bg-amber-600 hover:bg-amber-700 text-white font-medium rounded-2xl shadow-md transition duration-300"
    >
      {{ showMessage ? '감사합니다 🙏' : '덕담 받기 💌' }}
    </button>

    <!-- 덕담 메시지 -->
    <transition name="fade">
      <div v-if="showMessage" class="mt-6 text-xl text-amber-700 font-semibold animate-fade-in">
        올해도 행복이 가득하시길 바랍니다 🎁
      </div>
    </transition>

    <!-- 바닥글 -->
    <footer class="absolute bottom-4 text-sm text-amber-600 opacity-70">
      © 2025 한가위 프로젝트 | Made with 🍂 Vue + TypeScript + Vite
    </footer>
  </div>
</template>

<script setup lang="ts">
import { ref } from 'vue'

const showMessage = ref(false)
</script>

<style scoped>
@keyframes fade-in {
  from {
    opacity: 0;
    transform: translateY(10px);
  }
  to {
    opacity: 1;
    transform: translateY(0);
  }
}

.animate-fade-in {
  animation: fade-in 1s ease-in-out;
}

.fade-enter-active,
.fade-leave-active {
  transition: opacity 0.5s;
}

.fade-enter-from,
.fade-leave-to {
  opacity: 0;
}
</style>
